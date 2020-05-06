

### embyonekey

- Qunhui emby suite version server 1.5 key Bai Yan
- Click on the left and click on the right

# Talk ahead
You won't mess with anything
<br/>and so~~~
<br/>Please ensure that no new virtual host is created in Web Station
<br/>Please follow the instructions to set the path correctly
<br/>I'm not responsible for any problems
<br/>Can't see the picture or the script can't be downloaded and run
<br/>Please science well raw.githubusercontent.com URL

### Step description
<br/>0. Install Web Station and EMBY in Qunhui
<br/>1. Open Web Station and create a new virtual host as shown
<br><img src="https://github.com/s1oz/embyonekey/blob/master/webstation.png"><br>
<br/>2. Open Qunhui Control Panel-Security-Certificate
<br/>Click New-Add New Certificate-Import Certificate-Select the downloaded private key and certificate
<br/>Certificate download address
```
https://raw.githubusercontent.com/s1oz/embyonekey/master/mb3admin.com.cert.pem
https://raw.githubusercontent.com/s1oz/embyonekey/master/mb3admin.com.key.pem
```
<br><img src="https://github.com/s1oz/embyonekey/blob/master/cert0.png"><br>
<br/>3. After saving, set the mb3admin.com certificate to the one just imported in the configuration
<br><img src="https://github.com/s1oz/embyonekey/blob/master/cert1.png"><br>


#### Hijack mb3admin pseudo-station

If the NAS address of the fake station is 10.0.0.10, fill it in as follows, and modify it according to your actual situation.The purpose is to hijack the domain name to the fake station.

    10.0.0.10 mb3admin.com
	
If you are hijacking a route, no other settings are required
If there is no route hijacking, you need to modify each client hijacking

0. op class routing can add additional hosts file directly in the route
<br/>Log into ssh and enter the following command
`vi /etc/myhosts`
<br/>i enter edit state
<br/>Enter `10.0.0.10 mb3admin.com`
`:wq` Save and exit
<br/>Login op
<br/>Click on Network-HOSTS and parse files-Add additional HOSTS files
`/etc/myhosts`
<br/>Save effective
1. Qunhui can directly log in to modify
<br/>Log into ssh and enter the following command
`vi /etc/hosts`
<br/>i enter edit state
<br/>Enter `10.0.0.10 mb3admin.com`
`:wq` Save and exit
2. Windows modification is just a different path
<br/>Open the `C:\Windows\System32\drivers\etc\`directory directly
<br/>Modify the hosts file in the folder
	
### Next run this script


Execute commands as root user：<br/>
</p><pre><code>wget -N --no-check-certificate "https://raw.githubusercontent.com/s1oz/embyonekey/master/embyonekey.sh" && chmod +x embyonekey.sh && ./embyonekey.sh</code></pre>

<br/>Finished
<br/>You can enter the following command to test
```
nginx -t
```
Check if an error is reported

```
curl https://mb3admin.com/admin/service/registration/validateDevice
curl https://mb3admin.com/admin/service/registration/validateDevice/666
```
Run the command in ssh to check whether the return value is correct

#### I wish you all fun

<br/>As shown in the figure, open to have a member yellow label
<br/>
<br/>![](https://github.com/s1oz/embyonekey/blob/master/ko.png)
<br/>
<br/>Enter any key in Emby Premiere to activate successfully
<br/>
<br/>![](https://github.com/s1oz/embyonekey/blob/master/ko1.png)

#### Client certificate installation
If the server fails to display correctly, the client still cannot be displayed correctly, generally the certificate is incorrect, please install the certificate on the client
```
https://raw.githubusercontent.com/s1oz/embyonekey/master/guomi.cer 
```
Download this certificate file named guomi.cer and install it on the corresponding device

Windows please install this directory
<br/>![](https://github.com/s1oz/embyonekey/blob/master/window.png)

<br/>IOS needs to trust the certificate in the settings-general-about mobile-certificate trust settings after installation


## Thank you Time Axis, Stars

