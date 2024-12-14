# Synology_NightScout_Easy
Synology Nightscout with Lets Encrypt and custom DDNS

Steps to create Synology DDNS and use Let's Encrypt to redirect to your nighscout instance. 

You will need to port forward ports 80 and 443 to your Synology NAS. Check the internet for how

For this example I'll be usinf DSM 7.x but the instructions should get you close on old versions. 


1. How to Access a Synology NAS Remotely with DDNS
1. First, ensure that you have a Synology Account. We will need this to get our free DDNS hostname. Open the Control Panel, go to Synology Account, then Sign in to or sign up for a Synology Account.

synology nas access remotely - synology account
2. After your account has been created, select External Access, DDNS, then Add.

3. Select the service provider as Synology, then select a Hostname that you’d like to use. This must be unique and is what you’ll use moving forward. In the drop-down menu, you will see a bunch of domains (synology.me, DiskStation.me, myDS.me, etc.). Select whichever you’d like to use, then select Test Connection. The test should report back as Normal.

4. If you’d like to get a certificate from Let’s Encrypt, you can select that checkbox. This will fetch a new certificate and set it as the default. 

5. If you keep the Enable Heartbeat checkbox selected, you will receive emails informing you when the DDNS connection is lost. Select OK to continue the creation.

If you enabled the Let’s Encrypt certificate checkbox, you will get a message stating that services that have used the existing default certificate might have to be updated. Select OK.

synology nas access remotely - getting a certificate
This is an example email you will receive if you keep the Enable Heartbeat checkbox selected.

heartbeat email sent if access is lost to the neas
If you need to update the services to use your new certificate, select Control Panel -> Security -> Certificate -> Settings. You can then go in and modify your services to use the correct certificate.

configuring a certificate in synology dsm
6. DDNS is now properly configured! At this point, the domain name you selected will ALWAYS be updated with your home’s external IP address as long as the Synology NAS is on and connected to the internet
