sauce:    https://github.com/s1oz/embyonekey
//  Not formatted

embyonekey
Qunhui emby suite version server 1.5 key Bai Yan
Click on the left and click on the right
Talk ahead
Han also not blind fiddle
so ~~~
Please ensure that does not in any Web Station in New Hosting
please follow the instructions to set the correct path
out of what I am not responsible for problems
not see the picture or script can not be downloaded to run
your good raw science .githubusercontent.com URL

Step description

0. installed in Web Station in Qunhui with EMBY
1. Open the New Web Hosting Web Station as shown in Figure 2. Open the Control Panel Qunhui - Security - Certificate private choose to download - Click New - Adds a new certificate - Import Certificate key with certificate Download certificate





https://raw.githubusercontent.com/s1oz/embyonekey/master/mb3admin.com.cert.pem
https://raw.githubusercontent.com/s1oz/embyonekey/master/mb3admin.com.key.pem



3. After saving, set the mb3admin.com certificate to the one just imported in the configuration


Hijack mb3admin pseudo-station
If the NAS address of the fake station is 10.0.0.10, fill it in as follows, and modify it according to your actual situation.The purpose is to hijack the domain name to the fake station.

10.0.0.10 mb3admin.com
If you are in the route hijacking, no other settings are required.If you are not in the route hijacking, you need to modify each client hijacking

op class routing can add additional hosts files directly in the route
landing ssh, enter the following command vi /etc/myhosts
i to enter edit mode
input 10.0.0.10 mb3admin.com :wqsave and exit
the landing op
click on the network -HOSTS and parse the file - adding extra HOSTS file /etc/myhosts
saved into force
Qunhui can log in directly modify the
landing ssh, enter the following command vi /etc/hosts
i to enter edit mode
input 10.0.0.10 mb3admin.com :wqsave and exit
Windows only modify different paths
directly open C:\Windows\System32\drivers\etc\directory
hosts file modify folder
Next run this script
Run the command as the root user:

wget -N --no-check-certificate "https://raw.githubusercontent.com/s1oz/embyonekey/master/embyonekey.sh" && chmod +x embyonekey.sh && ./embyonekey.sh

Has finished running,
you can enter the following command to test

nginx -t
Check if an error is reported

curl https://mb3admin.com/admin/service/registration/validateDevice
curl https://mb3admin.com/admin/service/registration/validateDevice/666
Run the command in ssh to check whether the return value is correct

I wish you all fun

As shown, you can have open membership yellow standard input any keys in Emby Premiere are successful can be activated







Client certificate installation
If the server fails to display correctly, the client still cannot be displayed correctly, generally the certificate is incorrect, please install the certificate on the client

https://raw.githubusercontent.com/s1oz/embyonekey/master/guomi.cer 
Download this certificate file named guomi.cer and install it on the corresponding device

Windows please install this directory



IOS needs to trust the certificate in the settings-general-about mobile-certificate trust settings after installation

Thanks to the time-axis star, the magic thought tutorial leads

