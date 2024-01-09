# EASY_MODE PRIVATE-LTE

tl;dr  - budget is $1400 or less

1. Go [here](https://www.coursera.org/learn/google-cbrs-cpi-training) and get a certification.
2. Buy one of [these](https://na.baicells.com/product/Details?id=d45a2d0a-5dae-41ff-8ffc-8906ec052245) or one of [these](https://store.baicells.com/product/Details?id=c7b62a86-c748-4b71-aeb4-3f01bed0b026).
3. Buy some [SIM Cards](https://store.baicells.com/product/Details?id=3288579c-1dcd-4722-a097-d5aafbd0593b)
4. Get a pixel 4 or another [compatible device](https://ongoalliance.org/certification/fcc-authorized-end-user/). Make really really sure it's unlocked. I can't stress that enough. Unlocked.
5. Create account on [cloudcore](https://cloudcore.baicells.com:4443/)
6. Create account on [google's SAS thingy](https://wirelessconnectivity.google.com/sas/org/7036890946131537609/project/18e4a41e-a86f-44ab-be76-b9c2e15523d6?pli=1&authuser=1&m=m&l=42.67213,-70.50615,958767a,0t,0h&tab=sites&view=table&stackView=)
7. Activate/configure your baicell eNodeB (aka - cell tower) on cloudcore and SAS. [Use this youtube video](https://youtu.be/Rcz8r24J4g8?t=1052) at 17:30 or so into the video.
8. Activate your SIM Card in cloudcore.
9. Stick SIM into pixel 4.
10. Party!

# Each step further explained

# Administration

# Equipment Purchases

You now need to purchase some private LTE based equipment. The lowest friction way I found to get ahold of this gear is to buy stuff from Baicell. There are some other vendors of private LTE gear that you can find with google.

## Vendors
You can find the full list on the FCC's website [here](https://apps.fcc.gov/oetcf/eas/reports/GenericSearch.cfm) and putting "CBD" in equipment class field

 - [Baicell](https://na.baicells.com)
 - [Blinq Networks](https://blinqnetworks.com/)
 - [Sercomm](https://www.sercomm.com/contpage.aspx?langid=1&type=prod2new&L1id=2&L2id=1&L3id=107)
 - Ericsson
 - Samsung

Good luck finding or purchasing the samsung and ericsson stuff though. Sounds like it would be difficult. Baicell's resellers were easy to work with, quote me gear, and get it to me. So that's what I went with.

## Core Equipment

### EnodeB (Tower)
An enodeb is a fancy LTE term for "Cell Phone Tower".  This is the main item you need to get your hands on. I purchased the [Nova 430i](https://na.baicells.com/product/Details?id=cb09870c-365e-472e-8766-69672100a250) but I don't have any real religion with it compared to others. The one problem you'll find with the "_i_" models is that they probably don't have the same range as the ones that allow you to bring your own antenna.


### Bridges (ethernet to lte)
You can get a lot of vendors that will sell you either ethernet to LTE or wife to LTE, similar to what t-mobile and verizon are selling now. These make testing a lot easier, and since they can broadcast at higher power levels, you can get further reach than a phone potentially.

Baicell sells these bridges, but again, they are also available from other vendors as well.

### Phones/UE

If you want to use your own phone, make sure you get one from this [list here](https://ongoalliance.org/certification/fcc-authorized-end-user/). This is a list of certified devices that will speak on something called "Band 42". Band 42 is the frequency range set aside for all private LTE comms. Also make sure to get an unlocked phone, since a locked phone might not allow you to use it on your private LTE network. You will literally look like a competing carrier. I used a Googel Pixel 4 since it was cheap on the used market.

### SIM cards
You also need some SIM cards. If you want to make your life easy, buy the SIM cards that Baicell also sells, since they can be activated with their own "packet core". More on that later. But basically think of it like a SaaS for your LTE management plane. It's pretty important that if you want to get started, you buy the SIM cards that will go with your connected SaaS based core.

# certification
## CPI Courses
If you want to run your own private LTE network, you need to become a "Certified Professional Installer". This is a real thing, and it gives you the ability to install, connect, and run a LTE network. Think of it like a ham license. It costs $600 dollars and is only available through certain groups. The least friction way to get certified is [Google's Coursera course](https://www.coursera.org/learn/google-cbrs-cpi-training).

## Certificate



# Software Services
## Cloud Based EPC
Once you get your stuff, you will want to activate an account on Baicell's "cloudcore" system. This allows you to manage your LTE equipment, activate SIM cards, and hook into the spectrum assignment stuff that you'll also have to enable.

## Spectrum Assignment System (SAS)
Now you want to activate a Spectrum  Assignment System. I suggest you use google's version of it again, since once again, it is all online and requires no human interaction. 

# FAQ

## What is easy mode?
Easy mode is offloading as much of the cognitive load of understanding the giant spaghetti mess of LTE networks onto someone else and making it their problem. Mobile networks need something known as "the core" which manages the interrelationship between multiple towers, billing, access, metering, etc. You can offload 90% of that to a SaaS offering by a few manufacturers, which gets you from "I have a bunch of gear" to "I have a working network." The trade off is that they charge a small fee ($1.00 / UE / Month) that you could save if you operated your own network ("Packet Core").

## can't get nova 430i to GPS Sync

having issues with `Cell Status`?
Google SAS says everything is hunky dory?

go into BTC Settings -> Sync Settings and set `sync mode` to `FREE_RUNNING` that appears to solve it. I hit this at defcon when struggling to get a signal. The default is for the eNodeB to use GPS to get clock sync, this appears to say "hold my beer" when it comes to timing. There's another option for NTP, but that appeared to "not work" as far as I could tell. 

## adding a phone number (phone and text) - DID
Once you get your LTE network up and running eventually you might want a phone number, either for two factor or just to bootstrap google voice. The cheapest and most reliable option I've used for years is (voip.ms)[https://voip.ms]. You can setup to charge only by the minute and only do SIP/RTP VoiP (no phone), but if you pay a little more you can get a DID (Direct Inward Dial or something.... A phone number) attached to it. After that you can get a new default dialer app for your phone, I found one called zoiper that seems to work great. I even get text messaging working through.

So the way you want to set this is the following:
1. go to voip.ms
2. create account
3. from main menu select account information to find your SIP/IAX settings
4. download and install zoiper
5. setup account to match, if you are using voip.ms, it would be something 111111@newyork1.voip.ms for user, and password is password
6. you should be able to dial another phone as long as your carrier doesn't block weird looking caller ID's (it might)
7. voip.ms can also end up blocking you accessing its services if it doesn't recognize a new voip client or source IP, so watch out for that. If that happens it'll be sent as an email and also in settings->security.
8. under default DID set the server to the one closet to you
9. top of menu, select DID Numbers. order a DID.
10. you can then manage your DID numbers under "manage"
11. now call your number from another phone. Should ring :). If it isn't ringing or shows as busy, make sure your DID server is the same as the one the phone's registered with. Otherwise you'll only be able to call out and receive anything.
12. You should be able to make and receive texts but no pictures today. I would recommend just using the number to setup google voice or signal instead of figuring that out. You can get a 3rd part app that'll do pictures in your texts using their API gateway. Up to you.

### cost

The cost for a DID / mo is $0.85 plus a flat feed of $0.009 (9/10th's of a cent) per minute for calls. It's probably the cheapest calling plan you can find on the planet. You can also opt in on e911, it costs an additinoal $1.50 / mo. I think this setup costs me maybe $35 / year?
