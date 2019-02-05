- - -
  [Français](index-fr.html)&nbsp;
  [English](index.html)&nbsp;
- - -
OpenVPN
-------
If OpenVPN connections are being blocked in your country, please refer to the [OpenVPN (stunnel)](/openvpn/stunnel.html) instructions instead which will help you wrap your OpenVPN traffic in an encrypted tunnel so it looks like standard TLS traffic.
#### A note on client files ####
For security reasons, this OpenVPN has been configured to only allow one client connection per certificate pair. Attempting to re-use client certificates will cause an existing client session to disconnect.

---
* Platforms
  * [Windows](#windows)
  * [macOS](#macos)
  * [Linux](#linux)
  * [Linux (Ubuntu 16.04)](#linux-ubuntu-16.04)
  * [Linux (Ubuntu 17.10)](#linux-ubuntu-17.10)
  * [Linux (Ubuntu 18.04/18.10)](#linux-ubuntu-18.04)
  * [Android](#android)
  * [iOS](#ios)

<a name="windows"></a>
### Windows ###
1. Download and run the OpenVPN [Windows Installer](/mirror/#openvpn).
1. Click *Next* and accept the license agreement by selecting *I Agree*.
1. Click *Next* on the *Choose Components* screen. Leave all of the default options checked.
1. Make note of the Destination Folder. This is where you will place the `52.15.254.140-direct.ovpn` client configuration profile after installation. Click *Install*.
1. A Windows Security notice will appear and ask *Would you like to install this device software?*. Click *Install*.
1. Click *Next* on the *Installation Complete* screen.
1. Uncheck *Show Readme* and click *Finish*.
1. Right-click on the OpenVPN GUI desktop icon and choose *Properties*.
1. Go to the *Compatibility* tab and click the *Run this program as an administrator* checkbox in the *Privilege Level* section.
1. Double-click the OpenVPN GUI desktop icon to launch the application.
1. Download one of these unified OpenVPN profiles:
   * [brother-various](/openvpn/brother-various/52.15.254.140-direct.ovpn)
   * [shallow-exotic](/openvpn/shallow-exotic/52.15.254.140-direct.ovpn)
   * [uncle-task](/openvpn/uncle-task/52.15.254.140-direct.ovpn)
   * [script-pizza](/openvpn/script-pizza/52.15.254.140-direct.ovpn)
   * [rely-inherit](/openvpn/rely-inherit/52.15.254.140-direct.ovpn)
   * *[Alternate profiles](#sslh-profiles) are available if you are on a network that only allows access to port `443`.*
   * *[UDP profiles](#udp-profiles) available.*
   * *[Combined profiles](#combined-profiles) are now available.*
1. Open the *config* directory that is located in the Destination Folder. For most users, this will either be in *C:\Program Files\OpenVPN\config* or *C:\Program Files (x86)\OpenVPN\config*. You will see a single README file in this directory.
1. Drag and drop the downloaded `52.15.254.140-direct.ovpn` file to this location alongside the README.
1. Right-click on the OpenVPN icon in your taskbar and choose *Connect*.
1. You will see a log scroll by as the connection is established, followed by a taskbar notification indicating your assigned IP.
1. Success! You can verify that your traffic is being routed properly by [looking up your IP address on DuckDuckGo](https://duckduckgo.com/?q=ip+address). It should say *Your public IP address is 52.15.254.140*.

<a name="macos"></a>
### macOS ###
1. Download and open [Tunnelblick](/mirror/#openvpn).
1. Type your password to allow the installation process to complete, and click *OK*.
1. Click *Launch* after the installation is finished.
1. Click *I have configuration files*.
1. Download one of these unified OpenVPN profiles:
   * [brother-various](/openvpn/brother-various/52.15.254.140-direct.ovpn)
   * [shallow-exotic](/openvpn/shallow-exotic/52.15.254.140-direct.ovpn)
   * [uncle-task](/openvpn/uncle-task/52.15.254.140-direct.ovpn)
   * [script-pizza](/openvpn/script-pizza/52.15.254.140-direct.ovpn)
   * [rely-inherit](/openvpn/rely-inherit/52.15.254.140-direct.ovpn)
   * *[Alternate profiles](#sslh-profiles) are available if you are on a network that only allows access to port `443`.*
   * *[UDP profiles](#udp-profiles) available.*
   * *[Combined profiles](#combined-profiles) are now available.*
1. Double-click the OpenVPN profile.
1. You will be asked to choose whether the profile should be available for all users or only the current user. After making your selection, you will be asked to enter your password.
1. Look for the Tunnelblick icon in your menu bar. Click on it, and choose *Connect*.
1. Success! You can verify that your traffic is being routed properly by [looking up your IP address on DuckDuckGo](https://duckduckgo.com/?q=ip+address). It should say *Your public IP address is 52.15.254.140*.

<a name="linux"></a>
### Linux ###
1. Install OpenVPN:

   `sudo apt-get install openvpn` OR `sudo yum install openvpn` OR `esoteric-package-manager hipster openvpn`

   * If installing OpenVPN via your package manager is not an option, you can also download and compile the [OpenVPN source code](/mirror/#openvpn).
1. Download one of these unified OpenVPN profiles:
   * [brother-various](/openvpn/brother-various/52.15.254.140-direct.ovpn)
   * [shallow-exotic](/openvpn/shallow-exotic/52.15.254.140-direct.ovpn)
   * [uncle-task](/openvpn/uncle-task/52.15.254.140-direct.ovpn)
   * [script-pizza](/openvpn/script-pizza/52.15.254.140-direct.ovpn)
   * [rely-inherit](/openvpn/rely-inherit/52.15.254.140-direct.ovpn)
   * *[Alternate profiles](#sslh-profiles) are available if you are on a network that only allows access to port `443`.*
   * *[UDP profiles](#udp-profiles) available.*
   * *[Combined profiles](#combined-profiles) are now available.*
1. Copy the downloaded `52.15.254.140-direct.ovpn` file to the location of your choice. */etc/openvpn/* is a decent option.
1. On some distributions, the pushed DHCP DNS option from the OpenVPN server will be ignored. This means that your DNS queries will still be routed through your ISP's servers which makes them vulnerable to what is known as a DNS leak.
   * You can test whether or not your DNS is leaking [here](https://dnsleaktest.com/).
   * You can ensure that the correct DNS servers are used by adding the following lines to the top of the `52.15.254.140-direct.ovpn` file:
     * `script-security 2`
     * `up /etc/openvpn/update-resolv-conf`
     * `down /etc/openvpn/update-resolv-conf`
1. Execute OpenVPN, and pass it the .ovpn profile as an option.

   `sudo openvpn 52.15.254.140-direct.ovpn`
1. Success! You can verify that your traffic is being routed properly by [looking up your IP address on DuckDuckGo](https://duckduckgo.com/?q=ip+address). It should say *Your public IP address is 52.15.254.140*.

<a name="linux-ubuntu-16.04"></a>
### Linux (Ubuntu 16.04) ###
Due to an issue related to Ubuntu 16.04's NetworkManager you cannot use the OpenVPN plugin. Additionally, you cannot use the version of OpenVPN which is in the default repositories. To fix this issue we must download OpenVPN directly from the projects repository.

1. Download one of these unified OpenVPN profiles:
   * [brother-various](/openvpn/brother-various/52.15.254.140-direct.ovpn)
   * [shallow-exotic](/openvpn/shallow-exotic/52.15.254.140-direct.ovpn)
   * [uncle-task](/openvpn/uncle-task/52.15.254.140-direct.ovpn)
   * [script-pizza](/openvpn/script-pizza/52.15.254.140-direct.ovpn)
   * [rely-inherit](/openvpn/rely-inherit/52.15.254.140-direct.ovpn)
   * *[Alternate profiles](#sslh-profiles) are available if you are on a network that only allows access to port `443`.*
   * *[UDP profiles](#udp-profiles) available.*
   * *[Combined profiles](#combined-profiles) are now available.*
1. Copy the downloaded `52.15.254.140-direct.ovpn` file to the location of your choice. */etc/openvpn/* is a decent option.
1. Add the OpenVPN APT repository to your sources by running the following commands:

   `curl -s https://swupdate.openvpn.net/repos/repo-public.gpg | apt-key add`
   `echo "deb http://build.openvpn.net/debian/openvpn/stable xenial main" > /etc/apt/sources.list.d/openvpn-aptrepo.list`
1. Update and install OpenVPN with the following command:

   `sudo apt update && sudo apt install openvpn`
1. After the install is complete, ensure you have OpenVPN version 2.4+ with the following command:

   `openvpn --version`
1. On some distributions, the pushed DHCP DNS option from the OpenVPN server will be ignored. This means that your DNS queries will still be routed through your ISP's servers which makes them vulnerable to what is known as a DNS leak.
   * You can test whether or not your DNS is leaking [here](https://dnsleaktest.com/).
   * You can ensure that the correct DNS servers are used by adding the following lines to the top of the `52.15.254.140-direct.ovpn` file:
     * `script-security 2`
     * `up /etc/openvpn/update-resolv-conf`
     * `down /etc/openvpn/update-resolv-conf`
1. Execute OpenVPN, and pass it the .ovpn profile as an option.

   `sudo openvpn 52.15.254.140-direct.ovpn`
1. Success! You can verify that your traffic is being routed properly by [looking up your IP address on DuckDuckGo](https://duckduckgo.com/?q=ip+address). It should say *Your public IP address is 52.15.254.140*.

<a name="linux-ubuntu-17.10"></a>
### Linux (Ubuntu 17.10) ###
It's preferable to configure Ubuntu using the OpenVPN plugin for NetworkManager. This gives you a nice little interface for connecting, and it properly handles the necessary DNS changes when you connect/disconnect. Unfortunately, the plugin does not support .ovpn profiles, so the list of steps is a little more involved.

1. First, download the OpenVPN CA certificate, the certificate `.crt` file, private key `.key` file, and TLS authentication key `ta.key` file for one of the client profiles below:
   * brother-various
      * CA Cert: [ca.crt](/openvpn/brother-various/ca.crt)
      * Client Cert: [brother-various.crt](/openvpn/brother-various/client.crt)
      * Client Key: [brother-various.key](/openvpn/brother-various/client.key)
      * TA key: [ta.key](/openvpn/brother-various/ta.key)
   * shallow-exotic
      * CA Cert: [ca.crt](/openvpn/shallow-exotic/ca.crt)
      * Client Cert: [shallow-exotic.crt](/openvpn/shallow-exotic/client.crt)
      * Client Key: [shallow-exotic.key](/openvpn/shallow-exotic/client.key)
      * TA key: [ta.key](/openvpn/shallow-exotic/ta.key)
   * uncle-task
      * CA Cert: [ca.crt](/openvpn/uncle-task/ca.crt)
      * Client Cert: [uncle-task.crt](/openvpn/uncle-task/client.crt)
      * Client Key: [uncle-task.key](/openvpn/uncle-task/client.key)
      * TA key: [ta.key](/openvpn/uncle-task/ta.key)
   * script-pizza
      * CA Cert: [ca.crt](/openvpn/script-pizza/ca.crt)
      * Client Cert: [script-pizza.crt](/openvpn/script-pizza/client.crt)
      * Client Key: [script-pizza.key](/openvpn/script-pizza/client.key)
      * TA key: [ta.key](/openvpn/script-pizza/ta.key)
   * rely-inherit
      * CA Cert: [ca.crt](/openvpn/rely-inherit/ca.crt)
      * Client Cert: [rely-inherit.crt](/openvpn/rely-inherit/client.crt)
      * Client Key: [rely-inherit.key](/openvpn/rely-inherit/client.key)
      * TA key: [ta.key](/openvpn/rely-inherit/ta.key)
1. Install the OpenVPN plugin for NetworkManager.

   `sudo apt-get install network-manager-openvpn-gnome`
1. Open your *System Settings*.
1. Click the *Network* tab on the left side.
1. Click the *+* button under *VPN*.
1. Select *OpenVPN*.
1. Enter `streisand-demo-site` for the *Name*.
1. Enter `52.15.254.140` for the *Gateway*.
1. Make sure *Certificates (TLS)* is selected for the *Type*.
1. Select the `client.crt` file you downloaded for the *User Certificate*.
1. Select the `ca.crt` file you downloaded for the *CA Certificate*.
1. Select the `client.key` file you downloaded for the *Private Key*.
1. Click the *Advanced* button.
1. Go to the *General* tab.
   * Check *Use custom gateway port* and enter `636` as its value.
     * Port `443` is available as an alternative if you are on a network that only allows access to the standard HTTPS port.
     * You can also use port `8757` for a UDP connection.
     * A combined profile which cycles through UDP port `8757`, TCP port `636` and `443` is also available.
   * Check *Use a TCP connection* unless you have chosen to use the UDP port or the combined profile.
1. Go to the *Security* tab.
   * Select `AES-256-CBC` as the *Cipher*.
   * Select `SHA256` as the *HMAC Authentication*.
1. Go to the *TLS Authentication* tab.
   * Under *Server Certificate Check* choose `verify name exactly` and enter `smooth-bonus-maple` as its value.
   * Check *Verify peer (server) certificate usage signature*.
   * Go to *Additional TLS authentication or encryption*.
     * Select `TLS-Crypt` as the *Mode*.
     * Select the `ta.key` file you downloaded from the client-files directory for the *Key File*.
   * Click *OK*.
1. Click *Add*
1. Select the VPN in the left-hand menu, and flip the switch to *ON*. You can also enable/disable the VPN by clicking on the WiFi/Network icon in the menu bar, scrolling to *VPN Connections*, and clicking on its name.
1. Success! You can verify that your traffic is being routed properly by [looking up your IP address on DuckDuckGo](https://duckduckgo.com/?q=ip+address). It should say *Your public IP address is 52.15.254.140*.

<a name="linux-ubuntu-18.04"></a>
### Linux (Ubuntu 18.04/18.10) ###
It's preferable to configure Ubuntu using the OpenVPN plugin for NetworkManager. This gives you a nice little interface for connecting, and it properly handles the necessary DNS changes when you connect/disconnect. Unfortunately, the plugin does not support .ovpn profiles, so the list of steps is a little more involved.

1. First, download the OpenVPN CA certificate, the certificate `.crt` file, private key `.key` file, and TLS authentication key `ta.key` file for one of the client profiles below:
   * brother-various
      * CA Cert: [ca.crt](/openvpn/brother-various/ca.crt)
      * Client Cert: [brother-various.crt](/openvpn/brother-various/client.crt)
      * Client Key: [brother-various.key](/openvpn/brother-various/client.key)
      * TA key: [ta.key](/openvpn/brother-various/ta.key)
   * shallow-exotic
      * CA Cert: [ca.crt](/openvpn/shallow-exotic/ca.crt)
      * Client Cert: [shallow-exotic.crt](/openvpn/shallow-exotic/client.crt)
      * Client Key: [shallow-exotic.key](/openvpn/shallow-exotic/client.key)
      * TA key: [ta.key](/openvpn/shallow-exotic/ta.key)
   * uncle-task
      * CA Cert: [ca.crt](/openvpn/uncle-task/ca.crt)
      * Client Cert: [uncle-task.crt](/openvpn/uncle-task/client.crt)
      * Client Key: [uncle-task.key](/openvpn/uncle-task/client.key)
      * TA key: [ta.key](/openvpn/uncle-task/ta.key)
   * script-pizza
      * CA Cert: [ca.crt](/openvpn/script-pizza/ca.crt)
      * Client Cert: [script-pizza.crt](/openvpn/script-pizza/client.crt)
      * Client Key: [script-pizza.key](/openvpn/script-pizza/client.key)
      * TA key: [ta.key](/openvpn/script-pizza/ta.key)
   * rely-inherit
      * CA Cert: [ca.crt](/openvpn/rely-inherit/ca.crt)
      * Client Cert: [rely-inherit.crt](/openvpn/rely-inherit/client.crt)
      * Client Key: [rely-inherit.key](/openvpn/rely-inherit/client.key)
      * TA key: [ta.key](/openvpn/rely-inherit/ta.key)
1. Install the OpenVPN plugin for NetworkManager.

   `sudo apt-get install network-manager-openvpn-gnome`
1. Open your *System Settings*.
1. Click the *Network* tab on the left side.
1. Click the *+* button under *VPN*.
1. Select *OpenVPN*.
1. Enter `streisand-demo-site` for the *Connection name*.
1. Enter `52.15.254.140` for the *Gateway*.
1. Make sure *Certificates (TLS)* is selected for the *Type*.
1. Select the `ca.crt` file you downloaded for the *CA Certificate*.
1. Select the `client.crt` file you downloaded for the *User Certificate*.
1. Select the `client.key` file you downloaded for the *User Private Key*.
1. Click the *Advanced* button.
1. Go to the *General* tab.
   * Check *Use custom gateway port* and enter `636` as its value.
     * Port `443` is available as an alternative if you are on a network that only allows access to the standard HTTPS port.
     * You can also use port `8757` for a UDP connection.
     * A combined profile which cycles through UDP port `8757`, TCP port `636` and `443` is also available.
   * Check *Use a TCP connection* unless you have chosen to use the UDP port or the combined profile.
1. Go to the *Security* tab.
   * Select `AES-256-CBC` as the *Cipher*.
   * Select `SHA256` as the *HMAC Authentication*.
1. Go to the *TLS Authentication* tab.
   * Under *Server Certificate Check* choose `verify name exactly` and enter `smooth-bonus-maple` as its value.
   * Check *Verify peer (server) certificate usage signature*.
   * Go to *Additional TLS authentication or encryption*.
     * Select `TLS-Crypt` as the *Mode*.
     * Select the `ta.key` file you downloaded from the client-files directory for the *Key File*.
   * Click *OK*.
1. Click *Add*
1. Find the VPN and flip the switch to *ON*. You can also enable/disable the VPN by clicking on the WiFi/Network icon in the menu bar, scrolling to *VPN Connections*, and clicking on its name.
1. Success! You can verify that your traffic is being routed properly by [looking up your IP address on DuckDuckGo](https://duckduckgo.com/?q=ip+address). It should say *Your public IP address is 52.15.254.140*.

<a name="android"></a>
### Android ###
1. Install [OpenVPN for Android](https://play.google.com/store/apps/details?id=de.blinkt.openvpn).
1. Download one of these unified OpenVPN profiles:
   * [brother-various](/openvpn/brother-various/52.15.254.140-direct.ovpn)
   * [shallow-exotic](/openvpn/shallow-exotic/52.15.254.140-direct.ovpn)
   * [uncle-task](/openvpn/uncle-task/52.15.254.140-direct.ovpn)
   * [script-pizza](/openvpn/script-pizza/52.15.254.140-direct.ovpn)
   * [rely-inherit](/openvpn/rely-inherit/52.15.254.140-direct.ovpn)
   * *[Alternate profiles](#sslh-profiles) are available if you are on a network that only allows access to ports `80` and `443`.*
   * *[UDP profiles](#udp-profiles) available.*
   * *[Combined profiles](#combined-profiles) are now available.*
1. Copy the `52.15.254.140-direct.ovpn` file to your phone.
1. Launch OpenVPN for Android.
1. Tap the folder icon in the lower-right of the screen.
1. Select the `52.15.254.140-direct.ovpn` profile that you copied to your phone.
1. Tap the save icon (floppy disk) in the lower-right of the screen after the import is complete.
1. Tap the profile.
1. Accept the Android VPN connection warning.
1. Success! You can verify that your traffic is being routed properly by [looking up your IP address on DuckDuckGo](https://duckduckgo.com/?q=ip+address). It should say *Your public IP address is 52.15.254.140*.

<a name="ios"></a>
### iOS ###
1. Download [OpenVPN Connect](https://itunes.apple.com/us/app/openvpn-connect/id590379981) and launch it.
1. Download one of these unified OpenVPN profiles:
   * [brother-various](/openvpn/brother-various/52.15.254.140-direct.ovpn)
   * [shallow-exotic](/openvpn/shallow-exotic/52.15.254.140-direct.ovpn)
   * [uncle-task](/openvpn/uncle-task/52.15.254.140-direct.ovpn)
   * [script-pizza](/openvpn/script-pizza/52.15.254.140-direct.ovpn)
   * [rely-inherit](/openvpn/rely-inherit/52.15.254.140-direct.ovpn)
   * *[Alternate profiles](#sslh-profiles) are available if you are on a network that only allows access to ports `80` and `443`.*
   * *[UDP profiles](#udp-profiles) available.*
   * *[Combined profiles](#combined-profiles) are now available.*
1. Open iTunes on your computer and connect your phone.
1. Select your phone, click on the *Apps* tab, and find OpenVPN under the *File Sharing* section.
1. Drag and drop the downloaded `52.15.254.140-direct.ovpn` file into the file sharing window.
1. OpenVPN on your phone will say that *1 new OpenVPN profile is available for import*.
1. Tap the green *+* button to import the profile.
1. Tap the slider to connect to the OpenVPN server.
1. Success! You can verify that your traffic is being routed properly by [looking up your IP address on DuckDuckGo](https://duckduckgo.com/?q=ip+address). It should say *Your public IP address is 52.15.254.140*.

<a name="sslh-profiles"></a>
### Alternate unified profiles for access via port 443 ###
* [brother-various](/openvpn/brother-various/52.15.254.140-sslh.ovpn)
* [shallow-exotic](/openvpn/shallow-exotic/52.15.254.140-sslh.ovpn)
* [uncle-task](/openvpn/uncle-task/52.15.254.140-sslh.ovpn)
* [script-pizza](/openvpn/script-pizza/52.15.254.140-sslh.ovpn)
* [rely-inherit](/openvpn/rely-inherit/52.15.254.140-sslh.ovpn)

<a name="udp-profiles"></a>
### Alternate unified profiles for access via UDP port 8757 ###
* [brother-various](/openvpn/brother-various/52.15.254.140-direct-udp.ovpn)
* [shallow-exotic](/openvpn/shallow-exotic/52.15.254.140-direct-udp.ovpn)
* [uncle-task](/openvpn/uncle-task/52.15.254.140-direct-udp.ovpn)
* [script-pizza](/openvpn/script-pizza/52.15.254.140-direct-udp.ovpn)
* [rely-inherit](/openvpn/rely-inherit/52.15.254.140-direct-udp.ovpn)

<a name="combined-profiles"></a>
### Alternate profile that will cycle through UDP port 8757, TCP port 636, and TCP port 443 ###
* [brother-various](/openvpn/brother-various/52.15.254.140-combined.ovpn)
* [shallow-exotic](/openvpn/shallow-exotic/52.15.254.140-combined.ovpn)
* [uncle-task](/openvpn/uncle-task/52.15.254.140-combined.ovpn)
* [script-pizza](/openvpn/script-pizza/52.15.254.140-combined.ovpn)
* [rely-inherit](/openvpn/rely-inherit/52.15.254.140-combined.ovpn)