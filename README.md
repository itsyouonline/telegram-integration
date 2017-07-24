# telegram-integration

## goal

- show how to integrate robot with IYO & create some demo robot using this feature

## integration process

- onboarding on IYO
  - user registers (is already on telegram) in IYO by using IYO bot
    - user got invited to the IYO registration bot by an invitation link
    - bot checks if the user is already known to IYO and all info required is there, if not then nothing to do
  - bot send user a https link to IYO and asks user to do or complete the registration
    - asks for addr, mobile, email & username (oauth2)
    - in the link the id info from telegram is there, so IYO can link IYO account to telegram ID
    - 2-factor authentication needs to be forced
  
-  a new example telegram bot shows how to authenticate against IYO and even ask OTP verification
  - people get invited to a demo bot
  - demo bot checks that user is known & demo bot is part of organization which can see the info from the user
  - demo bot shows the user info (email, tel, username, addr)
  - demo bot asks user to verify data (is all ok)
  - demo bot can now check from IYO last time user did succesful 2-factor auth (new API endpoint on IYO, see from each user time of last OTP verification), can optionally give telegram userid as argument so that IYO can re-verify telegram integration when returning this info (this makes sure the bot knows for sure, this user telegram has been auth < certain time)
  - show time since last auth
  - give user option to re-verify: just to show it works
  - do the authentication on IYO by sending right login url (telegram id needs to be in, this does re-verification)
  - bot keeps on polling the IYO authentication API (see above) that the user did it, if not done < 1 min ask again, ... untill user is online.

## iyo bot (v2)

- this bot gives people support on IYO
- this bot allows peope to register on IYO without having to go to IYO website
