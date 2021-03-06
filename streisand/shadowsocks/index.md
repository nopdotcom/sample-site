- - -
  [Français](index-fr.html)&nbsp;
  [English](index.html)&nbsp;
- - -
Shadowsocks
-----------

---
* Platforms
  * [Windows](#windows)
  * [macOS](#macos)
  * [Linux](#linux)
  * [Android](#android)
  * [iOS](#ios)
* Plugins
  * [simple-obfs](#simple-obfs)

<a name="windows"></a>
### Windows ###
1. Download [Shadowsocks for Windows](/mirror/shadowsocks/).
1. Extract the archive, and double-click on the Shadowsocks.exe file.
1. Make sure the QR code below is centered and completely visible, right-click on the Shadowsocks system tray icon, and go to *Servers* > *Scan QRCode from Screen...*

   ![Shadowsocks QR code](/shadowsocks/shadowsocks-qr-code.png)
1. You may also go to *Servers* > *New server* and manually complete the following steps:
   1. Enter `52.15.254.140` as the *Server IP*.
   1. Enter `8530` as the *Server Port*.
   1. Enter `kIHCO+d+WwlYhQGPRC2AVsvxP+qaJJxVYQ/6nVv1ecfcAa3UlZwftnswTFqwx2Pz` as the *Password*.
   1. The *SOCKS 5 Proxy Port* should be `1080` and the *Encryption Method* should be `chacha20-ietf-poly1305`.
   1. Click *Save*.
1. Click on the Shadowsocks menu tray icon and select *Enable*.
1. That's it! You can verify that your traffic is being routed properly by [looking up your IP address on DuckDuckGo](https://duckduckgo.com/?q=ip+address). It should say *Your public IP address is 52.15.254.140*.

<a name="macos"></a>
### macOS ###
1. Download [ShadowsocksX-NG](/mirror/shadowsocks/).
1. Double-click the ZIP, and extract the application into your Applications folder.
1. Launch ShadowsocksX-NG. You will be prompted to enter your password so that your system proxy settings can be modified.
1. Look for the Shadowsocks paper plane icon in your menu bar and click on it.
1. Make sure the QR code below is centered and completely visible, and choose *Scan QR Code from Screen...*

   ![Shadowsocks QR code](/shadowsocks/shadowsocks-qr-code.png)
1. You may also configure the connection by going to *Servers*, selecting *Open Server Preferences...*, and clicking the *+* button on the sidebar:
   1. Enter `52.15.254.140` and `8530` in the *Address* fields.
   1. Make sure `chacha20-ietf-poly1305` is selected for the *Encryption* value.
   1. Enter `kIHCO+d+WwlYhQGPRC2AVsvxP+qaJJxVYQ/6nVv1ecfcAa3UlZwftnswTFqwx2Pz` as the *Password*.
   1. Click *OK*.
1. Click on the Shadowsocks icon in the menu bar again, and choose *Global Mode*.
1. You can use the Shadowsocks icon to enable/disable the VPN. The color of the icon will change based on whether or not it is active.
1. That's it! You can verify that your traffic is being routed properly by [looking up your IP address on DuckDuckGo](https://duckduckgo.com/?q=ip+address). It should say *Your public IP address is 52.15.254.140*.

<a name="linux"></a>
### Linux ###
Download [shadowsocks2-linux-x64.gz](/mirror/shadowsocks/) and extract it:

    `gunzip shadowsocks2-linux-x64.gz`

Make the binary executable:

    `chmod +x shadowsocks2-linux-x64`

Start the shadowsocks SOCKS proxy:

    `./shadowsocks2-linux-x64 -c 52.15.254.140:8530 -password "kIHCO+d+WwlYhQGPRC2AVsvxP+qaJJxVYQ/6nVv1ecfcAa3UlZwftnswTFqwx2Pz" -socks localhost:1080 -verbose -cipher chacha20-ietf-poly1305`

For reference, this is the configuration specified:

        Server: 52.15.254.140
        Port: 8530
        Password: kIHCO+d+WwlYhQGPRC2AVsvxP+qaJJxVYQ/6nVv1ecfcAa3UlZwftnswTFqwx2Pz
        Encryption Method: chacha20-ietf-poly1305

Once you have Shadowsocks running locally, you'll need to forward your browser traffic through the SOCKS proxy it provides

### Testing with Curl

You can quickly test using curl:

     `curl -I --socks5 localhost:1080 google.com`

This should return a 301 Found response **not** a connection refused error.

#### Configuring Firefox to connect through a SOCKS proxy ####
1. Click the *Menu* button next to the *Home* icon to the right of the address bar.
1. Click *Options*.
1. Click the *Advanced* icon.
1. Go to the *Network* tab.
1. Click the *Settings* button to *Configure how Firefox connects to the Internet*.
1. Choose *Manual proxy configuration*.
1. Enter `127.0.0.1` and Port `1080` on the *SOCKS Host* line.
1. Select *Remote DNS*. This configures Firefox to send all DNS requests through the SOCKS proxy. This will protect you against DNS poisoning and ensure that false DNS entries cannot be used to censor your access.
1. Click *OK*.
1. Click *OK* again to close the Firefox preferences window.
1. You should be good to go! You can verify that your traffic is being routed properly by [looking up your IP address on DuckDuckGo](https://duckduckgo.com/?q=ip+address). It should say *Your public IP address is 52.15.254.140*.


<a name="android"></a>
### Android ###
1. Download Shadowsocks for Android from [Google Play](https://play.google.com/store/apps/details?id=com.github.shadowsocks). If Google Play is blocked in your country, you can [download a mirrored copy](/mirror/shadowsocks/) from this server!
1. Launch the application.
1. Tap the Add Profile *+* icon, second from the top-right of the screen.
1. Select *Scan QR code*.
1. Use your phone to scan this image, or if you are using your phone _right now_ you can choose the *Manual Settings* option and copy and paste the information from the Linux section above:

   ![Shadowsocks QR code](/shadowsocks/shadowsocks-qr-code.png)
1. Tap the round paper plane icon along the bottom-left bar.
1. Accept the Android VPN connection warning.
1. You can verify that your traffic is being routed properly by [looking up your IP address on DuckDuckGo](https://duckduckgo.com/?q=ip+address). It should say *Your public IP address is 52.15.254.140*.

<a name="ios"></a>
### iOS ###
1. Download [Shadowrocket](https://itunes.apple.com/us/app/shadowrocket/id932747118?mt=8) and launch it.
   > **Note:** Shadowrocket is not available in the China App Store.
1. Tap the QR code import icon in the top-left of the screen.
1. Use your phone to scan this image, or if you are using your phone _right now_ you can manually add a new proxy by tapping *Add Server* and using the information from the Linux section above:

   ![Shadowsocks QR code](/shadowsocks/shadowsocks-qr-code.png)
1. Toggle the connection switch located to the right of the *Not Connected* text on the *Home* tab.
   * If this is your first time running Shadowrocket, iOS will ask you to verify that the application should have permission to add VPN configurations. Tap *Allow* and follow the instructions.
1. You can verify that your traffic is being routed properly by [looking up your IP address on DuckDuckGo](https://duckduckgo.com/?q=ip+address). It should say *Your public IP address is 52.15.254.140*.

<a name="simple-obfs"></a>
### simple-obfs for unreliable/hostile networks ###
For users on unreliable or hostile networks (esp. experiencing quality-of-service (QOS) throttling) using the simple-obfs plugin may help alleviate these issues. Further configuration of the Shadowsocks client to use the simple-obfs plugin can be carried out via the following configuration:

        Server: 52.15.254.140
        Port: 8530
        Password: kIHCO+d+WwlYhQGPRC2AVsvxP+qaJJxVYQ/6nVv1ecfcAa3UlZwftnswTFqwx2Pz
        Encryption Method: chacha20-ietf-poly1305
        Plugin: obfs-local
        Plugin_Options: obfs=http;obfs-host=www.github.com

Android users will first need to download the [Simple Obfuscation](https://play.google.com/store/apps/details?id=com.github.shadowsocks.plugin.obfs_local&hl=en) plugin app, and then modify the existing Streisand profile on your client to use this plugin. You can do this by hitting the edit button next to the profile, tapping the `Plugin` option at the bottom of the profile and selecting the "Simple obsfucation" plugin from the menu. Your Shadowsocks traffic will now be obfuscated as `http` traffic to `www.github.com`.
