- - -
  [Français](index-fr.html)&nbsp;
  [English](index.html)&nbsp;
- - -
Shadowsocks
-----------

---
* Plateformes
  * [Windows](#windows)
  * [macOS](#macos)
  * [Linux](#linux)
  * [Android](#android)
  * [iOS](#ios)
* Plugins
  * [simple-obfs](#simple-obfs)

<a name="windows"></a>
### Windows ###
1. Téléchargez [Shadowsocks pour Windows](/mirror/shadowsocks/index-fr.html).
1. Extrayez l'archive et double-cliquez sur le fichier Shadowsocks.exe.
1. Assurez-vous que le code QR ci-dessous est centré et complètement visible, cliquez avec le bouton droit de la souris sur l'icône de la barre d'état système de Shadowsocks, puis accédez à *Servers* > *Scan QRCode from Screen...*

   ![Shadowsocks QR code](/shadowsocks/shadowsocks-qr-code.png)
1. Vous pouvez également aller à *Servers* > *New server* et procédez manuellement aux étapes suivantes:
   1. Saisissez `52.15.254.140` pour le *Server IP*.
   1. Saisissez `8530` pour le *Server Port*.
   1. Saisissez `kIHCO+d+WwlYhQGPRC2AVsvxP+qaJJxVYQ/6nVv1ecfcAa3UlZwftnswTFqwx2Pz` pour le *Password*.
   1. Le *SOCKS 5 Proxy Port* devrait être `1080` et le *Encryption Method* devrait être `chacha20-ietf-poly1305`.
   1. Assurez-vous que le support de l'authentification unique (OTA) est activé.
   1. Cliquez *Save*.
1. Cliquez sur l'icône de la barre de menus Shadowsocks et sélectionnez *Enable*.
1. C'est tout! Vous pouvez vérifier que votre trafic est correctement routé par [recherche de votre adresse IP sur DuckDuckGo](https://duckduckgo.com/?q=ip+address). Il devrait dire *Votre adresse IP publique est 52.15.254.140*.

<a name="macos"></a>
### macOS ###
1. Téléchargez [ShadowsocksX-NG](/mirror/shadowsocks/index-fr.html).
1. Double-cliquez sur le DMG et faites glisser l'icône dans votre dossier Applications.
1. Lancez ShadowsocksX-NG. Vous serez invité à saisir votre mot de passe afin que vos paramètres de proxy système puissent être modifiés.
1. Tapez sur l'icône du l'avion en papier rond dans la barre inférieure gauche.
1. Assurez-vous que le code QR ci-dessous est centré et complètement visible, et choisissez *Scan QR Code from Screen...*

   ![Shadowsocks QR code](/shadowsocks/shadowsocks-qr-code.png)
1. Vous pouvez également configurer la connexion en allant sur *Servers*, sélectionnant *Open Server Preferences...*, et en cliquant le bouton *+* sur la barre latérale:
   1. Saisissez `52.15.254.140` et `8530` dans le champ *Address*.
   1. Assurez-vous que `chacha20-ietf-poly1305` est sélectionné pour la valeur *Encryption*.
   1. Saisissez `kIHCO+d+WwlYhQGPRC2AVsvxP+qaJJxVYQ/6nVv1ecfcAa3UlZwftnswTFqwx2Pz` pour le *Password*.
   1. Chocher `Enable OTA`.
   1. Cliquez *OK*.
1. Cliquez à nouveau sur l'icône Shadowsocks dans la barre de menu, puis choisissez *Global Mode*.
1. Vous pouvez utiliser l'icône Shadowsocks pour activer/désactiver le VPN. La couleur de l'icône changera en fonction de son activation ou pas.
1. C'est tout! Vous pouvez vérifier que votre trafic est correctement routé par [recherche de votre adresse IP sur DuckDuckGo](https://duckduckgo.com/?q=ip+address). Il devrait dire *Votre adresse IP publique est 52.15.254.140*.

<a name="linux"></a>
### Linux ###
Téléchargez [shadowsocks2-linux-x64.gz](/mirror/shadowsocks/index-fr.html) et extrayez-le:

   `gunzip shadowsocks2-linux-x64.gz`

Modifier le binaire qu'il soit exécutable

    `chmod +x shadowsocks2-linux-x64`

Démarrez le proxy SOCKS shadowsocks:

    `./shadowsocks2-linux-x64 -c 52.15.254.140:8530 -password "kIHCO+d+WwlYhQGPRC2AVsvxP+qaJJxVYQ/6nVv1ecfcAa3UlZwftnswTFqwx2Pz" -socks localhost:1080 -verbose -cipher chacha20-ietf-poly1305`


Pour référence, voici les informations de configuration dont vous aurez besoin:

        Server: 52.15.254.140
        Port: 8530
        Password: kIHCO+d+WwlYhQGPRC2AVsvxP+qaJJxVYQ/6nVv1ecfcAa3UlZwftnswTFqwx2Pz
        Encryption Method: chacha20-ietf-poly1305

Une fois que vous avez Shadowsocks fonctionnant localement, vous devrez transférer le trafic de votre navigateur via le proxy SOCKS qu'il fournit.

#### Configuration de Firefox pour se connecter via un proxy SOCKS ####
1. Cliquez sur le bouton *Menu* à côté de l'icône *Accueil* à droite de la barre d'adresse.
1. Cliquez *Préférences*.
1. Cliquez l'icône *Avancé*.
1. Allez à l'onglet *Réseau*.
1. Cliquez le bouton *Paramètres* pour *Configurer la façon dont Firefox se connecte à Internet*.
1. Choisissez *Configuration manuelle de proxy*.
1. Saisissez `127.0.0.1` et port `1080` pour la ligne *Hôte SOCKS*.
1. Sélectionnez *Utiliser un DNS distant lorsque SOCKS v5 est actif*. Cela configure Firefox pour envoyer toutes les requêtes DNS via le proxy SOCKS. Cela vous protégera contre l'empoisonnement du DNS et vous garantira que les fausses entrées DNS ne peuvent pas être utilisées pour censurer votre accès.
1. Cliquez *OK*.
1. Cliquez *OK* encore pour fermer la fenêtre de paramètres de Firefox..
1. C'est tout! Vous pouvez vérifier que votre trafic est correctement routé par [recherche de votre adresse IP sur DuckDuckGo](https://duckduckgo.com/?q=ip+address). Il devrait dire *Votre adresse IP publique est 52.15.254.140*.


<a name="android"></a>
### Android ###
1. Téléchargez Shadowsocks pour Android à partir de [Google Play](https://play.google.com/store/apps/details?id=com.github.shadowsocks&hl=fr). Si Google Play est bloqué dans votre pays, vous pouvez [télécharger une copie en miroir](/mirror/shadowsocks/index-fr.html) de ce serveur!
1. Lancez l'application.
1. Tapez sur l'icône Ajouter un profil +, en haut à droite de l'écran.
1. Tapez l'icône *+* en bas à droite.
1. Sélectionnez *Scan QR code*.
1. Utilisez votre téléphone pour numériser cette image, ou si vous utilisez votre téléphone _maintenant_, vous pouvez choisir la *Manual Settings* et copiez/collez les informations à partir de la section Linux ci-dessus:

   ![Shadowsocks QR code](/shadowsocks/shadowsocks-qr-code.png)
1. Tapez sur l'icône de l'avion en haut.
1. Acceptez l'avertissement de connexion VPN Android.
1. Vous pouvez vérifier que votre trafic est correctement routé par [recherche de votre adresse IP sur DuckDuckGo](https://duckduckgo.com/?q=ip+address). Il devrait dire *Votre adresse IP publique est 52.15.254.140*.


<a name="ios"></a>
### iOS ###

1. Téléchargez [Shadowrocket](https://itunes.apple.com/fr/app/shadowrocket/id932747118?mt=8) et lancez-le.
   * Vous serez invité à vous connecter à l'iTunes Store la première fois que vous exécutez Shadowrocket.
   > **Note:** Shadowrocket n'est pas disponible dans l'App Store chinois
1. Appuyez sur l'icône d'importation du code QR en haut à gauche de l'écran.
1. Utilisez votre téléphone pour numériser cette image, ou si vous utilisez votre téléphone _maintenant_, vous pouvez ajouter manuellement un nouveau proxy à partir de l'onglet *Home* et copier et coller les informations de la section Linux ci-dessus:

   ![Shadowsocks QR code](/shadowsocks/shadowsocks-qr-code.png)
1. Mettez le commutateur de connexion situé à droite du texte *Not connected* sur l'onglet *Home*.
   * Si c'est la première fois que vous utilisez Shadowrocket, iOS vous demandera de vérifier que l'application devrait avoir la permission d'ajouter des configurations VPN. Tapez *Permettre* et suivez les instructions.
1. Vous pouvez vérifier que votre trafic est correctement routé par [recherche de votre adresse IP sur DuckDuckGo](https://duckduckgo.com/?q=ip+address). Il devrait dire *Votre adresse IP publique est 52.15.254.140*.

<a name="simple-obfs"></a>
### simple-obfs pour les réseaux peu fiables/hostiles ###
Pour les utilisateurs sur des réseaux peu fiables ou hostiles (en particulier la limitation de la qualité de service (QOS)), l'utilisation du plugin simple-obfs peut vous aider à atténuer ces problèmes. La configuration supplémentaire du client Shadowsocks pour utiliser le plugin simple-obfs peut être effectuée via la configuration suivante:

        Server: 52.15.254.140
        Port: 8530
        Password: kIHCO+d+WwlYhQGPRC2AVsvxP+qaJJxVYQ/6nVv1ecfcAa3UlZwftnswTFqwx2Pz
        Encryption Method: chacha20-ietf-poly1305
        Plugin: obfs-local
        Plugin_Options: obfs=http;obfs-host=www.github.com
Les utilisateurs d'Android devront d'abord télécharger l'application [Simple obfuscation] (https://play.google.com/store/apps/details?id=com.github.shadowsocks.plugin.obfs_local&hl=fr), puis modifier le profil existant de Streisand sur votre client pour utiliser ce plugin. Vous pouvez le faire en appuyant sur le bouton d'édition (edit) à côté du profil, en tapant l'option Plugin en bas du profil et en sélectionnant le plugin "Simple obfuscation" dans le menu. Votre trafic Shadowsocks sera maintenant obscurci en tant que http trafic vers www.github.com.