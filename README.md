<img src="https://user-images.githubusercontent.com/60521939/156067564-a7076955-684b-4082-8ec2-081b33fd6eee.jpeg" width="300">


# What is CallBouncer?

When unknown or unwanted callers attempt to call you, Call Bouncer will intelligently assess the situation and decide if the call should be put through to your mobile phone. 

Features include:
- Flexible forwarding. Forward all calls to CallBouncer, or just suspicious calls
- Make sure VIP callers (like your mom!) can reach you any time, for any reason
- Receive only high-priority calls to your mobile device
- Low priority callers are asked to send a text message instead
- Annoy annoying scammers with an annoying IVR


# Architecture

<img src="https://user-images.githubusercontent.com/60521939/156067561-7f49ff12-88cb-49ad-ad54-cd039ce792db.png" width="600">



# Prerequisites

You will need the following in order to get started:
1. [Twilio Account](https://www.twilio.com/console/projects/create)
2. iOS or Android mobile device 
   - Must have ability to forward calls
4. [Google Voice](https://voice.google.com/u/0/about) account
   - Account must be [linked to device mobile number](https://support.google.com/voice/answer/165221)
   - Mobile app must be installed and configured to receive incoming calls
   - (Optional) Configure [voicemail](https://support.google.com/voice/answer/115106?hl=en&ref_topic=1708439)


# Setup Instructions


## Setup Studio

1. [Create new Studio Flow](https://support.twilio.com/hc/en-us/articles/115015961327-Getting-Started-with-Twilio-Studio#create)
2. Edit the Studio flow JSON `CallBouncer` found in the `/studio` directory. 
3. Replace GOOGLEVOICENUMBER with your Google Voice number (e.164 format). 
4. Replace MOMSNUMBER with your mom's phone number (e.164 format). Save.
6. [Import](https://www.twilio.com/docs/studio/user-guide#importing-flow-data) the updated Studio flow JSON.
7. Save and publish Studio Flow.

## Provision and Configure Twilio Phone Number

1. Purchase one [phone number](https://www.twilio.com/console/phone-numbers/search) via the Twilio Console.
2. [Connect](https://www.twilio.com/docs/studio/user-guide/get-started#configure-a-twilio-phone-number-to-connect-to-a-studio-flow) the phone number to the Studio flow.

## Forward Default Mobile Phone to Twilio Number

1. Configure mobile device calling app to forward calls to the Twilio Number 
   - Forward all calls or use conditional forwarding to send declined calls to CallBouncer
   - [Instructions for Android](https://www.androidauthority.com/call-forwarding-android-870778/) 
   - [Instructions for iPhone](https://support.apple.com/guide/iphone/set-up-call-forwarding-and-call-waiting-iphe9bdd027a/ios))
2. The mobile phone number will now forward to the Twilio number, which may (optionally) forward to the Google Voice number.


## Optional Configurations

1. Add a [recorded greeting](https://www.twilio.com/docs/studio/widget-library/sayplay#play-a-message-configuration) for Mom
2. Add [additional transitions for VIPs](https://www.twilio.com/docs/studio/widget-library/split-based-on#split-based-on-transitions) (like your significant other or your boss) via widget `split_1`

