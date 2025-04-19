---
title: "Linking Sendgrid and Cloudflare DNS"
date: 2025-04-19T16:38:02+01:00
draft: false
tags:
- dns
- cloudflare
- sendgrid
- email
---
For this to make sense, I'm assuming that you have accounts with both `Cloudflare` as your DNS provider and `SendGrid` as your email provider. If not, hopefully some of this translates or is food for thought.

This was honestly a pain in the arse, mostly because of the feedback loops for seeing if DNS has worked is measured in _days_ and there are no good error messages other than 'not working' in SendGrid. This leaves you guessing and trawling the internet for things to try to get it working.  

The reasons for needing email in my app are the typical scenarios: 1) account creation 2) password resetting 3) communication (features / changes / news). 

The added benefit is the ability to brand links so the emails will be sent from `@london-property-pulse.com`. This is small but one of my favourite things to feel real / professional.

### Set up

#### 1. Create a non-Gmail account
This is something that SendGrid requires you to do. I chose Outlook, use whatever you like. What this means is that a lot of spammers use throw-away Gmail accounts and cannot be trusted with an email blaster. 

#### 2. Verify the email
You know the drill, just follow the steps SendGrid tell you to follow. 

#### 3. Adding the SendGrid DNS records to Cloudflare
This is the fun bit where you add a bunch of CNAME and a couple of TXT records, effectively hooking up `SendGrid` to `Cloudflare`. Keep in mind, when you're done it takes 1 - 2 days for changes to be registered by DNS servers.
When setting these up, make sure to turn off the Cloudflare special-sauce DNS proxying (orange cloud thing). This was half the reason I wasn't seeing the DNS resolve. 

##### Why Turn off DNS proxying? 
There are a number of reasons for this but, in a nutshell, the proxying prevents SSL cert validation on the origin server and reduces email deliverability due to the disruption of DKIM authentication. The second part means that your emails will all end up in spam folders 💩

#### 4. Turning on email routing in Cloudflare
This was a source of frustration and something I didn't turn on until much later. I couldn't understand why the DNS wasn't propagating despite triple checking for typos and processes. 

After turning on this setting under the Email tab in the Cloudflare dashboard, you're asked to add several email related MX type DNS records.  This is the second part of the magic to get things working. Without it your DNS server won't process email. You need to register an email for this, I used the same email as the one used to send and receive emails in `SendGrid`.   

To call it out, the issue was not due to CNAME flattening. Apparently this is an issue for some people and a setting that is not available to modify (read _turn-off_) for top level domains (e.g. `london-property-pulse.com`). It also makes no difference if your DNS server can resolve it, which apparently Cloudflare does. 

Additional context: when setting the CNAME values, SendGrid asks you to add a CNAME host like `xxx.london-property-pulse.com`, on save Cloudflare shortens it to just `xxx` in the console, also called CNAME flattening. 

More on that here: [CNAME flattening](https://developers.cloudflare.com/dns/cname-flattening/) 

#### 5. Checking DNS is working with email
There are 2 ways of doing this: 1) using the SendGrid verify button where the DNS records to configure are listed 2) using a 3rd party tool like DNSChecker.org.

I checked about once or twice a day to see if the DNS had resolved in `SendGrid` and `DNSChecker`, and then thinking of all the possible reasons why it hadn't. Definitely land-of-confusion moments! 

The old faithful here: [DNSChecker.org](https://dnschecker.org/)

#### Next steps and recommendations
I've not tested the sending of emails, but I'm glad to be out of settings dashboards / click-ops and back into code to get the email sending working.

I definitely recommend setting up the email DNS before you need it as it does take a while to get it working due to the slowness of propagation. It's also something that you can do in the background while working on other things. 

The good thing about DNS is that once it's configured it's set-and-forget!
