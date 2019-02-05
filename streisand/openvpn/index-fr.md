- - -
  [Français](index-fr.html)&nbsp;
  [English](index.html)&nbsp;
- - -
OpenVPN
-------
Si les connexions OpenVPN sont bloquées dans votre pays, reportez-vous aux instructions [OpenVPN (stunnel)](/openvpn/stunnel-fr.html) qui vous aideront à envelopper votre trafic OpenVPN dans un tunnel crypté afin qu'il ressemble à du trafic TLS standard.
#### Une note sur les fichiers clients ####
Pour des raisons de sécurité, ce serveur OpenVPN a été configuré pour n'autoriser qu'une seule connexion client par paire de certificats. Toute tentative de ré-utiliser les certificats clients entraînera une session client existante de se déconnecter.

---
* Plateformes
  * [Windows](#windows)
  * [macOS](#macos)
  * [Linux](#linux)
  * [Linux (Ubuntu 16.04)](#linux-ubuntu-16.04)
  * [Linux (Ubuntu 17.10)](#linux-ubuntu-17.10)
  * [Linux (Ubuntu 18.04)](#linux-ubuntu-18.04)
  * [Android](#android)
  * [iOS](#ios)

<a name="windows"></a>
### Windows ###

1. Téléchargez et exécutez [l'installateur Windows](/mirror/index-fr.html#openvpn) OpenVPN.
1. Cliquez sur *Suivant* et acceptez le contrat de licence en sélectionnant *J'accepte*.
1. Cliquez *Suivant* sur l'écran *Choose Components* (Choisir les composants). Laissez toutes les options par défaut cochées.
1. Notez le dossier de destination. C'est là que vous placerez le profil de configuration client `52.15.254.140-direct.ovpn` après l'installation. Cliquez sur *Install* (Installer).
1. Un avis de sécurité Windows apparaîtra et demande *Voulez-vous installer ce logiciel de périphérique?*. Cliquer *Installer*.
1. Cliquez *Next* sur l'écran *Installation Complete* (installation complète).
1. Décochez *Show Readme* puis cliquez *Finish* (finir).
1. Cliquez-droit sur l'icône OpenVPN GUI et choisissez *Propriétés*.
1. Allez à l'onglet *Compatibilité* et cochez la case *Exécuter ce programme en tant qu'administrateur* dans la section *Niveau du privilège*.
1. Double-cliquez sur l'icône OpenVPN GUI situé sur votre bureau afin de lancer l'application.
1. Téléchargez l'un de ces profils OpenVPN unifiés :
   * [brother-various](/openvpn/brother-various/52.15.254.140-direct.ovpn)
   * [shallow-exotic](/openvpn/shallow-exotic/52.15.254.140-direct.ovpn)
   * [uncle-task](/openvpn/uncle-task/52.15.254.140-direct.ovpn)
   * [script-pizza](/openvpn/script-pizza/52.15.254.140-direct.ovpn)
   * [rely-inherit](/openvpn/rely-inherit/52.15.254.140-direct.ovpn)
   * *[Profils alternatifs](#sslh-profiles) sont disponibles si vous êtes sur un réseau qui ne permet l'accès au port `443`.*
   * *[Profils UDP](#udp-profiles) sont disponibles.*
   * *[Profils combinés](#combined-profiles) sont maintenant disponibles.*
1. Ouvrez le répertoire *config* situé dans le dossier de destination. Pour la plupart des utilisateurs, ça sera *C:\Programmes\OpenVPN\config* ou *C:\Program Files (x86)\OpenVPN\config*. Vous verrez un seul fichier README dans ce répertoire.
1. Faites glisser et déposez le `52.15.254.140-direct.ovpn` téléchargé a ci-dessus, et placez-le dans le même répertoire que le fichier README.
1. Faites un clic droit sur l'icône OpenVPN dans la barre des tâches et choisissez *Connecter*.
1. Vous verrez des journaux se déplacent à mesure que la connexion est établie, suivie d'une notification de la barre des tâches indiquant votre adresse IP attribuée.
1. Succès ! Vous pouvez vérifier que votre trafic est correctement routé par [recherche de votre adresse IP sur DuckDuckGo](https://duckduckgo.com/?q=ip+address). Il devrait dire *Votre adresse IP publique est 52.15.254.140*.

<a name="macos"></a>
### macOS ###

1. Téléchargez et lancez [Tunnelblick](/mirror/index-fr.html#openvpn).
1. Saisissez votre mot de passe pour permettre le processus d'installation de finir, et cliquez ensuite sur *OK*.
1. Cliquez *Lancer* une fois l'installation terminée.
1. Cliquez *J'ai des fichiers de configuration*.
1. Téléchargez l'un des profils unifiés d'OpenVPN:
   * [brother-various](/openvpn/brother-various/52.15.254.140-direct.ovpn)
   * [shallow-exotic](/openvpn/shallow-exotic/52.15.254.140-direct.ovpn)
   * [uncle-task](/openvpn/uncle-task/52.15.254.140-direct.ovpn)
   * [script-pizza](/openvpn/script-pizza/52.15.254.140-direct.ovpn)
   * [rely-inherit](/openvpn/rely-inherit/52.15.254.140-direct.ovpn)
   * *[Profils alternatifs](#sslh-profiles) sont disponibles si vous êtes sur un réseau qui ne permet l'accès au port `443`.*
   * *[Profils UDP](#udp-profiles) sont disponibles.*
   * *[Profils combinés](#combined-profiles) sont maintenant disponibles.*
1. Double-cliquez le profil OpenVPN.
1. Vous devrez choisir si le profil doit être disponible pour tous les utilisateurs ou seulement pour l'utilisateur actuel. Après avoir effectué votre sélection, vous devrez entrer votre mot de passe.
1. Recherchez l'icône Tunnelblick dans votre barre de menus. Cliquez dessus et choisissez *Connecter*.
1. Succès ! Vous pouvez vérifier que votre trafic est correctement routé par [recherche de votre adresse IP sur DuckDuckGo](https://duckduckgo.com/?q=ip+address). Il devrait dire *Votre adresse IP publique est 52.15.254.140*.

<a name="linux"></a>
### Linux ###
1. Installer OpenVPN:

   `sudo apt-get install openvpn` où `sudo yum install openvpn` où `gestionnaire-de-paquetage-esoterique hipster openvpn`

   * Si l'installation de OpenVPN via votre gestionnaire de paquet n'est pas une option, vous pouvez également télécharger et compiler le [code source OpenVPN](/mirror/index-fr.html#openvpn).
1. Téléchargez l'un de ces profils OpenVPN unifiés :
   * [brother-various](/openvpn/brother-various/52.15.254.140-direct.ovpn)
   * [shallow-exotic](/openvpn/shallow-exotic/52.15.254.140-direct.ovpn)
   * [uncle-task](/openvpn/uncle-task/52.15.254.140-direct.ovpn)
   * [script-pizza](/openvpn/script-pizza/52.15.254.140-direct.ovpn)
   * [rely-inherit](/openvpn/rely-inherit/52.15.254.140-direct.ovpn)
   * *[Profils alternatifs](#sslh-profiles) sont disponibles si vous êtes sur un réseau qui permet uniquement l'accès au port `443`.*
   * *[Profils UDP](#udp-profiles) sont disponibles.*
   * *[Profils combinés](#combined-profiles) sont maintenant disponibles.*
1. Copiez le fichier `52.15.254.140-direct.ovpn` téléchargé vers l'emplacement de votre choix. */etc/openvpn/* est une bonne option.
1. Sur certaines distributions, l'option DNS DHCP poussée du serveur OpenVPN sera ignorée. Cela signifie que vos requêtes DNS seront toujours acheminées via les serveurs de votre FAI qui les rend vulnérables à ce que l'on appelle une fuite DNS.
   * Vous pouvez tester si votre DNS ou non est en train de fuir [ici](https://dnsleaktest.com/).
   * Vous pouvez vous assurer que les serveurs DNS corrects sont utilisés en ajoutant les lignes suivantes au début du fichier `52.15.254.140-direct.ovpn`:
     * `script-security 2`
     * `up /etc/openvpn/update-resolv-conf`
     * `down /etc/openvpn/update-resolv-conf`
1. Exécutez OpenVPN et passez le profil .ovpn en option.

   `sudo openvpn 52.15.254.140-direct.ovpn`
1. Succès ! Vous pouvez vérifier que votre trafic est correctement routé par [recherche de votre adresse IP sur DuckDuckGo](https://duckduckgo.com/?q=ip+address). Il devrait dire *Votre adresse IP publique est 52.15.254.140*.

<a name="linux-ubuntu-16.04"></a>
### Linux (Ubuntu 16.04) ###
En raison d'un problème lié à NetworkManager d'Ubuntu 16.04, vous ne pouvez pas utiliser le plug-in OpenVPN. De plus, vous ne pouvez pas utiliser la version de OpenVPN qui est dans les dépôts par défaut. Pour résoudre ce problème, nous devons télécharger OpenVPN directement depuis le dépôt de projets.

1. Téléchargez l'un de ces profils OpenVPN unifiés :
   * [brother-various](/openvpn/brother-various/52.15.254.140-direct.ovpn)
   * [shallow-exotic](/openvpn/shallow-exotic/52.15.254.140-direct.ovpn)
   * [uncle-task](/openvpn/uncle-task/52.15.254.140-direct.ovpn)
   * [script-pizza](/openvpn/script-pizza/52.15.254.140-direct.ovpn)
   * [rely-inherit](/openvpn/rely-inherit/52.15.254.140-direct.ovpn)
   * [Profils alternatifs](#sslh-profiles) sont disponibles si vous êtes sur un réseau qui permet uniquement l'accès au port `443`.*
   * [Profils UDP](#udp-profiles) sont disponibles.*
   * [Profils combinés](#combined-profiles) sont maintenant disponibles.*
1. Copiez le fichier téléchargé 52.15.254.140-direct.ovpn `à l'emplacement de votre choix. */etc/openvpn/* est une bonne option.
1. Ajouter le dépôt APT OpenVPN à vos sources en exécutant les commandes suivantes :

   `curl -s https://swupdate.openvpn.net/repos/repo-public.gpg | apt-key add`
   `echo "deb http://build.openvpn.net/debian/openvpn/stable xenial main" > /etc/apt/sources.list.d/openvpn-aptrepo.list`
1. Mettre à jour et installez OpenVPN avec la commande suivante :

   `sudo apt update && sudo apt install openvpn`
1. Une fois l'installation terminée, vérifiez que vous disposez de la version OpenVPN 2.4+ avec la commande suivante :

   `openvpn --version`
1. Dans certaines distributions, l'option DNS DHCP poussée du serveur OpenVPN sera ignorée. Cela signifie que vos requêtes DNS seront toujours acheminés par les serveurs de votre fournisseur de services Internet qui les rend vulnérables à ce qu'on appelle une fuite DNS.
   * Vous pouvez tester si votre DNS fuit ou non [ici](https://dnsleaktest.com/).
   * Vous pouvez vous assurer que les serveurs DNS corrects sont utilisés en ajoutant les lignes suivantes au début du fichier `52.15.254.140-direct.ovpn` :
     * `script-security 2`
     * `up /etc/openvpn/update-resolv-conf`
     * `down /etc/openvpn/update-resolv-conf`
1. Exécutez OpenVPN et transmettez-lui le profil .ovpn en option.

   `sudo openvpn 52.15.254.140-direct.ovpn`
1. Succès ! Vous pouvez vérifier que votre trafic est correctement routé par [recherche de votre adresse IP sur DuckDuckGo](https://duckduckgo.com/?q=ip+address). Il devrait dire *Votre adresse IP publique est 52.15.254.140*.

<a name="linux-ubuntu-17.10"></a>
### Linux (Ubuntu) ###
Il est préférable de configurer Ubuntu en utilisant le plugin OpenVPN pour NetworkManager. Cela vous donne une jolie petite interface pour la connexion, et il gère correctement les modifications DNS nécessaires lors de la connexion / déconnexion. Malheureusement, le plugin ne prend pas en charge les profils .ovpn, les étapes sont donc un peu plus compliquée.

1. Premièrement, téléchargez le certificat CA d'OpenVPN, le certificat client `.crt`, la clé privée du client `.key`, et finalement la clé d'authentification TLS `ta.key` pour l'un ces profils en dessous:
   * brother-various
      * CA Cert: [ca.crt](/openvpn/brother-various/ca.crt)
      * Client Cert: [brother-various.crt](/openvpn/brother-various/client.crt)
      * Client Clé: [brother-various.key](/openvpn/brother-various/client.key)
      * TA Clé: [ta.key](/openvpn/brother-various/ta.key)
   * shallow-exotic
      * CA Cert: [ca.crt](/openvpn/shallow-exotic/ca.crt)
      * Client Cert: [shallow-exotic.crt](/openvpn/shallow-exotic/client.crt)
      * Client Clé: [shallow-exotic.key](/openvpn/shallow-exotic/client.key)
      * TA Clé: [ta.key](/openvpn/shallow-exotic/ta.key)
   * uncle-task
      * CA Cert: [ca.crt](/openvpn/uncle-task/ca.crt)
      * Client Cert: [uncle-task.crt](/openvpn/uncle-task/client.crt)
      * Client Clé: [uncle-task.key](/openvpn/uncle-task/client.key)
      * TA Clé: [ta.key](/openvpn/uncle-task/ta.key)
   * script-pizza
      * CA Cert: [ca.crt](/openvpn/script-pizza/ca.crt)
      * Client Cert: [script-pizza.crt](/openvpn/script-pizza/client.crt)
      * Client Clé: [script-pizza.key](/openvpn/script-pizza/client.key)
      * TA Clé: [ta.key](/openvpn/script-pizza/ta.key)
   * rely-inherit
      * CA Cert: [ca.crt](/openvpn/rely-inherit/ca.crt)
      * Client Cert: [rely-inherit.crt](/openvpn/rely-inherit/client.crt)
      * Client Clé: [rely-inherit.key](/openvpn/rely-inherit/client.key)
      * TA Clé: [ta.key](/openvpn/rely-inherit/ta.key)
1. Installez le plugin OpenVPN pour NetworkManager.

   `sudo apt-get install network-manager-openvpn-gnome`
1. Ouvrez votre *Paramètres système*.
1. Cliquez sur l'icône *Réseau*.
1. Cliquez sur le bouton *+* en bas à gauche de la fenêtre.
1. Sélectionnez *VPN* dans la liste déroulante Interface et cliquez sur *Créer*.
1. Sélectionnez *OpenVPN* et cliquez *Créer*.
1. Saisissez `streisand-demo-site` pour la *Nom de la connexion*.
1. Saisissez `52.15.254.140` pour le *Gateway*.
1. Assurez-vous que *Certificates (TLS)* est sélectionné pour le *Type*.
1. Sélectionnez le fichier `client.crt` de votre choix pour le *User Certificate*.
1. Sélectionnez le fichier `ca.crt` pour le *CA Certificate*.
1. Sélectionnez le ficher `client.key` pour le *Private Key*.
1. Cliquez le bouton *Advanced*.
1. Accédez à l'onglet *General*.
   * Vérifier *Use custom gateway port* et entrer `636` comme sa valeur.
     * Port `443` est disponible en alternative si vous êtes sur un réseau qui ne permet l'accès au le port HTTPS standard.
     * Vous pouvez également utiliser le port `8757` pour une connexion UDP.
     * Le profil combiné qui parcourt le port UDP `8757`, le port TCP `636`et `443` est également disponible.
   * Cochez *Use a TCP connection* sauf si vous avez choisi d'utiliser le port UDP ou le profil combiné.
1. Accédez à l'onglet *Security*.
   * Sélectionnez `AES-256-CBC` pour le *Cipher*.
   * Sélectionnez `SHA256` pour le *HMAC Authentication*.
1. Accédez à l'onglet *TLS Authentication*.
   * Dans le menu déroulant *Server Certificate Check* selectionnez `verify name exactly` et saisissez `smooth-bonus-maple` pour sa valeur.
   * Cochez *Verify peer (server) certificate usage signature*.
   * Cochez *Additional TLS authentication or encryption*.
     * Sélectionnez `TLS-Crypt` pour *Mode*.
     * Sélectionnez le fichier `ta.key` que vous avez téléchargé depuis le répertoire client-files pour le *Key File*.
   * Cliquez *Valider*.
1. Cliquez *Enregistrer*
1. Sélectionnez le VPN dans le menu à gauche, et faites glisser l'interrupteur sur *ON*. Vous pouvez également activer/désactiver le VPN en cliquant sur l'icône WiFi/Réseau dans la barre de menu, défiler vers *Connexions VPN* et en cliquant sur son nom.
1. Succès ! Vous pouvez vérifier que votre trafic est correctement routé par [recherche de votre adresse IP sur DuckDuckGo](https://duckduckgo.com/?q=ip+address). Il devrait dire *Votre adresse IP publique est 52.15.254.140*.

<a name="linux-ubuntu-18.04"></a>
### Linux (Ubuntu) ###
Il est préférable de configurer Ubuntu en utilisant le plugin OpenVPN pour NetworkManager. Cela vous donne une jolie petite interface pour la connexion, et il gère correctement les modifications DNS nécessaires lors de la connexion / déconnexion. Malheureusement, le plugin ne prend pas en charge les profils .ovpn, les étapes sont donc un peu plus compliquée.

1. Premièrement, téléchargez le certificat CA d'OpenVPN, le certificat client `.crt`, la clé privée du client `.key`, et finalement la clé d'authentification TLS `ta.key` pour l'un ces profils en dessous:
   * brother-various
      * CA Cert: [ca.crt](/openvpn/brother-various/ca.crt)
      * Client Cert: [brother-various.crt](/openvpn/brother-various/client.crt)
      * Client Clé: [brother-various.key](/openvpn/brother-various/client.key)
      * TA Clé: [ta.key](/openvpn/brother-various/ta.key)
   * shallow-exotic
      * CA Cert: [ca.crt](/openvpn/shallow-exotic/ca.crt)
      * Client Cert: [shallow-exotic.crt](/openvpn/shallow-exotic/client.crt)
      * Client Clé: [shallow-exotic.key](/openvpn/shallow-exotic/client.key)
      * TA Clé: [ta.key](/openvpn/shallow-exotic/ta.key)
   * uncle-task
      * CA Cert: [ca.crt](/openvpn/uncle-task/ca.crt)
      * Client Cert: [uncle-task.crt](/openvpn/uncle-task/client.crt)
      * Client Clé: [uncle-task.key](/openvpn/uncle-task/client.key)
      * TA Clé: [ta.key](/openvpn/uncle-task/ta.key)
   * script-pizza
      * CA Cert: [ca.crt](/openvpn/script-pizza/ca.crt)
      * Client Cert: [script-pizza.crt](/openvpn/script-pizza/client.crt)
      * Client Clé: [script-pizza.key](/openvpn/script-pizza/client.key)
      * TA Clé: [ta.key](/openvpn/script-pizza/ta.key)
   * rely-inherit
      * CA Cert: [ca.crt](/openvpn/rely-inherit/ca.crt)
      * Client Cert: [rely-inherit.crt](/openvpn/rely-inherit/client.crt)
      * Client Clé: [rely-inherit.key](/openvpn/rely-inherit/client.key)
      * TA Clé: [ta.key](/openvpn/rely-inherit/ta.key)
1. Installez le plugin OpenVPN pour NetworkManager.

   `sudo apt-get install network-manager-openvpn-gnome`
1. Ouvrez votre *Paramètres système*.
1. Cliquez sur l'icône *Réseau*.
1. Cliquez sur le bouton *+* en bas à gauche de la fenêtre.
1. Sélectionnez *VPN* dans la liste déroulante Interface et cliquez sur *Créer*.
1. Sélectionnez *OpenVPN* et cliquez *Créer*.
1. Saisissez `streisand-demo-site` pour la *Nom de la connexion*.
1. Saisissez `52.15.254.140` pour le *Gateway*.
1. Assurez-vous que *Certificates (TLS)* est sélectionné pour le *Type*.
1. Sélectionnez le fichier `client.crt` de votre choix pour le *User Certificate*.
1. Sélectionnez le fichier `ca.crt` pour le *CA Certificate*.
1. Sélectionnez le ficher `client.key` pour le *Private Key*.
1. Cliquez le bouton *Advanced*.
1. Accédez à l'onglet *General*.
   * Vérifier *Use custom gateway port* et entrer `636` comme sa valeur.
     * Port `443` est disponible en alternative si vous êtes sur un réseau qui ne permet l'accès au le port HTTPS standard.
     * Vous pouvez également utiliser le port `8757` pour une connexion UDP.
     * Le profil combiné qui parcourt le port UDP `8757`, le port TCP `636`et `443` est également disponible.
   * Cochez *Use a TCP connection* sauf si vous avez choisi d'utiliser le port UDP ou le profil combiné.
1. Accédez à l'onglet *Security*.
   * Sélectionnez `AES-256-CBC` pour le *Cipher*.
   * Sélectionnez `SHA256` pour le *HMAC Authentication*.
1. Accédez à l'onglet *TLS Authentication*.
   * Dans le menu déroulant *Server Certificate Check* selectionnez `verify name exactly` et saisissez `smooth-bonus-maple` pour sa valeur.
   * Cochez *Verify peer (server) certificate usage signature*.
   * Cochez *Additional TLS authentication or encryption*.
     * Sélectionnez `TLS-Crypt` pour *Mode*.
     * Sélectionnez le fichier `ta.key` que vous avez téléchargé depuis le répertoire client-files pour le *Key File*.
   * Cliquez *Valider*.
1. Cliquez *Enregistrer*
1. Sélectionnez le VPN dans le menu à gauche, et faites glisser l'interrupteur sur *ON*. Vous pouvez également activer/désactiver le VPN en cliquant sur l'icône WiFi/Réseau dans la barre de menu, défiler vers *Connexions VPN* et en cliquant sur son nom.
1. Succès ! Vous pouvez vérifier que votre trafic est correctement routé par [recherche de votre adresse IP sur DuckDuckGo](https://duckduckgo.com/?q=ip+address). Il devrait dire *Votre adresse IP publique est 52.15.254.140*.

<a name="android"></a>
### Android ###

1. Installez [OpenVPN pour Android](https://play.google.com/store/apps/details?id=de.blinkt.openvpn&hl=fr).
1. Téléchargez l'un de ces profils OpenVPN unifiés :
   * [brother-various](/openvpn/brother-various/52.15.254.140-direct.ovpn)
   * [shallow-exotic](/openvpn/shallow-exotic/52.15.254.140-direct.ovpn)
   * [uncle-task](/openvpn/uncle-task/52.15.254.140-direct.ovpn)
   * [script-pizza](/openvpn/script-pizza/52.15.254.140-direct.ovpn)
   * [rely-inherit](/openvpn/rely-inherit/52.15.254.140-direct.ovpn)
   * *[Profils alternatifs](#sslh-profiles) sont disponibles si vous êtes sur un réseau qui permet uniquement l'accès au port `443`.*
   * *[Profils UDP](#udp-profiles) sont disponibles.*
   * *[Profils combinés](#combined-profiles) sont maintenant disponibles.*
1. Copiez le fichier `52.15.254.140-direct.ovpn` sur votre téléphone.
1. Lancez OpenVPN pour Android.
1. Appuyez sur l'icône du dossier en bas à droite de l'écran.
1. Sélectionnez le profil `52.15.254.140-direct.ovpn` que vous avez copié sur votre téléphone.
1. Tapez sur l'icône de sauvegarde (disquette) en bas à droite de l'écran une fois l'importation est terminée.
1. Tapez le profil.
1. Acceptez l'avertissement de connexion VPN Android.
1. Succès ! Vous pouvez vérifier que votre trafic est correctement routé par [recherche de votre adresse IP sur DuckDuckGo](https://duckduckgo.com/?q=ip+address). Il devrait dire *Votre adresse IP publique est 52.15.254.140*.

<a name="ios"></a>
### iOS ###

1. Téléchargez [OpenVPN Connect](https://itunes.apple.com/fr/app/openvpn-connect/id590379981) et lancez-le.
1. Téléchargez l'un de ces profils OpenVPN unifiés:
   * [brother-various](/openvpn/brother-various/52.15.254.140-direct.ovpn)
   * [shallow-exotic](/openvpn/shallow-exotic/52.15.254.140-direct.ovpn)
   * [uncle-task](/openvpn/uncle-task/52.15.254.140-direct.ovpn)
   * [script-pizza](/openvpn/script-pizza/52.15.254.140-direct.ovpn)
   * [rely-inherit](/openvpn/rely-inherit/52.15.254.140-direct.ovpn)
   * *[Profils alternatifs](#sslh-profiles) sont disponibles si vous êtes sur un réseau qui permet uniquement l'accès au port `443`.*
   * *[Profils UDP](#udp-profiles) sont disponibles.*
   * *[Profils combinés](#combined-profiles) sont maintenant disponibles.*
1. Ouvrez iTunes sur votre ordinateur et connectez votre téléphone.
1. Sélectionnez votre téléphone, cliquez sur l'onglet *Apps* et trouvez OpenVPN dans la section *Partage de fichiers*.
1. Faites glisser et déposez le fichier `52.15.254.140-direct.ovpn` téléchargé dans la fenêtre de partage de fichiers.
1. OpenVPN sur votre téléphone va vous dire *1 new OpenVPN profile is available for import*.
1. Appuyez sur le bouton vert *+* pour importer le profil.
1. Tapez sur le l'interrupteur pour vous connecter au serveur OpenVPN.
1. Succès! Vous pouvez vérifier que votre trafic est correctement routé par [recherche de votre adresse IP sur DuckDuckGo](https://duckduckgo.com/?q=ip+address). Il devrait dire *Votre adresse IP publique est 52.15.254.140*.

<a name="sslh-profiles"></a>
### Profils alternatifs unifiés pour l'accès via le port 443 ###

* [brother-various](/openvpn/brother-various/52.15.254.140-sslh.ovpn)
* [shallow-exotic](/openvpn/shallow-exotic/52.15.254.140-sslh.ovpn)
* [uncle-task](/openvpn/uncle-task/52.15.254.140-sslh.ovpn)
* [script-pizza](/openvpn/script-pizza/52.15.254.140-sslh.ovpn)
* [rely-inherit](/openvpn/rely-inherit/52.15.254.140-sslh.ovpn)

<a name="udp-profiles"></a>
### Profils alternatifs unifiés pour accéder via le port UDP 8757 ###

* [brother-various](/openvpn/brother-various/52.15.254.140-direct-udp.ovpn)
* [shallow-exotic](/openvpn/shallow-exotic/52.15.254.140-direct-udp.ovpn)
* [uncle-task](/openvpn/uncle-task/52.15.254.140-direct-udp.ovpn)
* [script-pizza](/openvpn/script-pizza/52.15.254.140-direct-udp.ovpn)
* [rely-inherit](/openvpn/rely-inherit/52.15.254.140-direct-udp.ovpn)

<a name="combined-profiles"></a>
### Profil alternatif qui parcourra le port UDP 8757, le port TCP 636, et le port TCP 443 ###

* [brother-various](/openvpn/brother-various/52.15.254.140-combined.ovpn)
* [shallow-exotic](/openvpn/shallow-exotic/52.15.254.140-combined.ovpn)
* [uncle-task](/openvpn/uncle-task/52.15.254.140-combined.ovpn)
* [script-pizza](/openvpn/script-pizza/52.15.254.140-combined.ovpn)
* [rely-inherit](/openvpn/rely-inherit/52.15.254.140-combined.ovpn)
