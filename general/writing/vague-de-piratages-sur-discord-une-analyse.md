## Abstract
Ce document décrit la marche à suivre en cas de piratage de compte.
À la fin, le document décrira comment éviter ce genre d'attaques dans le futur.

## Sommaire

* 1 Vérifications
  * 1.1 Vérifier si un compte est compromis
* 2 En cas de compromission
  * 2.1 Si vous avez toujours accès au compte
  * 2.2 Résolution
  * 2.3 Si vous êtes déconnecté·e de Discord
* 3 Détection et analyse
  * 3.1 Comment savoir si un site Web est légitime
  * 3.2 Analyse des moyens mis en œuvre pour attirer des utilisateurs
  * 3.3 Analyse du fonctionnement technique du virus
    * 3.3.1 Fonctionnement de Discord
    * 3.3.2 Fonctionnement du virus
      * 3.3.2.1 La partie Discord
      * 3.3.2.2 La partie en dehors de Discord
* 4 Mitigations
* 5 Fin

## 1 Vérifications

### 1.1 Vérifier si un compte est compromis

La vérification est assez simple.
Pour cela, ouvrez un explorateur de fichiers (`explorer.exe`) et allez dans le chemin suivant:
`%localappdata%\Discord`
Ici, il devrait y avoir un dossier `app-` suivit d'un numéro de version. Accèdez a ce dossier.
Vérifiez si il y a un dossier nommé `PirateStealer` ou quelque chose contenant `Stealer` dans le nom.
Si cela est le cas, il y a deux méthodes.
La première est de réinstaller complètement Discord.
La seconde est décrite dans le point 2.2 de la section 2 de ce document.

## 2 En cas de compromission

### 2.1 Si vous avez toujours accès au compte

Si vous avez toujours accès a votre compte Discord, activez l'authentification à deux facteurs et changez votre mot de passe et passez à la section 2.2 Mitigation.

### 2.2 Mitigation

Si dans l'étape 1.1 la présence d'un de ces logiciels malveillants est détectée, veuillez procéder de la sorte.

1. Installez un éditeur texte puissant tel que [Notepad++](https://notepad-plus-plus.org/)
2. Rendez-vous dans le chemin de fichier précédemment décrit dans la section 1.1 de ce document
3. Supprimez tous les dossiers suivant le schéma suivant: `stealer;grabber`
4. Ouvrez le fichier `index.js` avec votre éditeur de texte
5. Remplacez le contenu de ce fichier par:

```javascript
module.exports = require('./core.asar');
```
6. Redémarrez Discord
7. Re-changez votre mot de passe si ce n'est pas déjà fait

### 2.3 Si vous êtes déconnectés de Discord

Dans ce cas, veuillez ouvrir une demande au [support de Discord](https://support.discord.com/hc/en-us) contenant toutes les informations du compte (sauf votre mot de passe).

## 3 Détection et analyse

### 3.1 Comment savoir si un site Web est légitime

Les arnaques et piratages de ce genre sont de plus en plus difficiles a détecter.
L'analyse de celui-ci montre des attaquants organisés ayant un site web avec un domaine personalisé, entrainant de la crédibilité pour celui-ci.

Voici une capture d'écran du site des attaquants (2022/01/20) :
![Capture d'écran du site Web des attaquants](https://pads.jae.fi/uploads/upload_3e2561ed1ac816fbb9bee0f0d1f10fdc.png)
Comme vous pouvez le voir, le design donne un site crédible au premier regard.

En survolant le bouton "Télécharger", vous pouvez voir que l'addresse est redirigée vers le CDN de Discord et non un emplacement sur le site ce qui en soit peut être un facteur de détection.
![](https://pads.jae.fi/uploads/upload_9c592ec13c6d65672d6704133a8a262c.png)

Le site donne aussi un compte Twitter que vous pouvez voir ici en capture d'écran (nitter.snopyta.org; 2022/01/20) :

![Capture d'écran du compte Twitter des attaquants.](https://pads.jae.fi/uploads/upload_73225fd4bca221fbc7fc04c72372a8d4.png)

Comme vous pouvez le voir, le compte n'a que deux posts, mimant une activité réelle de développement de jeux vidéos.
Aucun autre détail n'est donné sur ce compte, il sert de facade pour attirer les utilisateurs.

Le nom de domaine du site est lui enregistré chez Ionos (1&amp;1). Vous pouvez retrouver ces données sur who.is par exemple.
![Capture d'écran du whois du domaine utilisé par les attaquants](https://pads.jae.fi/uploads/upload_942dc1dd42ad2132b967d726e087d469.png)
Comme vous pouvez le constater, le nom de domaine n'est enregistré que depuis le 2022/01/13 ce qui retire encore plus de sa crédibilité.

Le site web lui-même est hebergé chez Ionos (1&amp;1) en utilisant probablement l'offre gratuite venant avec l'achat d'un nom de domaine.
![](https://pads.jae.fi/uploads/upload_ceeb7457f0aaa4c25ea391fdc38045ff.png)

### 3.2 Analyse des moyens mis en oeuvre pour attirer des utilisateurs

Comme vous pouvez le constater, cette "mode" des virus dit "token-grabber" (attrapeurs de tokens) ne fait que s'emplifier depuis le mois dernier.
Ce qui est passé d'une partie mineure des piratages Discord est maintenant pris très au sérieux par les attaquants, allant jusqu'à acheter des noms de domaines afin de masquer leurs intentions sous une couverture très crédible aux premiers abords.

Les premier "virus" ayant pour but de voler un token d'authentification étaient plus proches d'igénérie sociale.
Quelqu'un se faisant passer pour le support de Discord vous demandais d'ouvrir l'onglet réseau des outils de débug afin de copier le token.

Ceux-cis ont aussi connu une nouvelle vague de popularité lors de l'implémentation des QR-codes afin de se connecter plus rapidement a l'aide d'un téléphone mobile.

Ces mêmes grabbers sont maintenants distribués sous forme d'éxécutables Microsoft Windows (`.exe`) ayant des fonctionalités multiples (voir section 3.3 pour plus de details).
Les premiers cas en cascade d'utilisation de ce genre de logiciels remonte à décembre 2021.

Il apparait que les comptes piratés par ce virus sont ensuit utilisés afin de le propager encore plus.
Voici quelques messages type envoyés. Est en rouge l'attaquant, en jaune la cible.
![](https://pads.jae.fi/uploads/upload_523567adf41764759106793daaadcf0d.png)
![](https://pads.jae.fi/uploads/upload_081a99ad81f4782d0ff58125f995ff48.png)
![](https://pads.jae.fi/uploads/upload_2fe44345350f26ad87c5aa2e59952521.png)
![](https://pads.jae.fi/uploads/upload_1d1af18b42e091daaa04f353aa04c58a.png)
![](https://pads.jae.fi/uploads/upload_79b25d7cea27ec2f5730640311effc1a.png)
![](https://pads.jae.fi/uploads/upload_653b2fefbdf23069316962f043396d85.png)


### 3.3 Analyse du fonctionnement technique du virus

#### 3.3.1 Fonctionnement de Discord

Afin d'authentifier ses utilisateurs, Discord utilise un système de [JSON Web Token](https://en.wikipedia.org/wiki/JSON_Web_Token) (ou JWT).
Changer un mot de passe régénère tous les tokens présents sur le compte et donc invalide les anciens.
C'est pour cette raison que la plupart des grabbers vont tenter de changer le mot de passe au plus vite pour bloquer l'accès au compte de la victime.

#### 3.3.2 Fonctionnement du virus

Comme décrit dans la section 3.2, l'éxécutable se présente sous la forme d'un fichier binaire éxécutable Win32 (Windows).
![](https://pads.jae.fi/uploads/upload_ba56419ab1e8b71a131ca0e7f1d58d43.png)
Aprés une analyse et une décompilation sommaire, il se trouve que cet éxécutable est en fait un bundle de NodeJS contenant une application JavaScript, probablement générée par [nexe](https://www.npmjs.com/package/nexe) et [pkg](https://www.npmjs.com/package/pkg).
Il est a noter qu'aucune version Linux ou macOS n'est à signaler au 2022/01/20.

L'application est souvent distribuée au travers des messages privés de Discord mais aussi de plus en plus par des sites Web dédiés (voir section 3.1).

Six versions du virus sont en cours d'analyse:
- Version 1 du 2022/01/14 (neutralisée)
- Version 2 du 2022/01/16
- Version 3 du 2022/01/20 (neutralisée)
- Version 4 du 2022/01/20
- Version 5 du 2022/01/22 (neutralisée)
- Version 6 du 2022/01/23

En utilisant la commande `grep` tout en extrayant les strings du fichier executable, nous pouvont trouver une URL vers un webhook Discord.
![](https://pads.jae.fi/uploads/upload_5988fe19d0b8d2cabb0b29f31d00ac1a.png)

Mise à jour du 2022/01/23: cette technique de détection n'est plus possible car la partie du code responsable a été obfusquée.


##### 3.3.2.1 La partie Discord

La partie Discord du virus est relativement simple.
Aprés éxécution, il injecte du code malicieux dans le processus en cours de Discord mais aussi dans le fichier `index.js` de l'application qui est chargée au lancement.
C'est ce chargement au lancement qui permet au virus de pouvoir compromettre plusieurs comptes en utilisant le même client Discord.
Cette méthode est aussi utilisée pour charger du code permettant de modifier Discord comme [BetterDiscord](https://github.com/BetterDiscord/BetterDiscord).

Après décompilation d'un de ces éxécutables, nous pouvons voir qu'il envoie des données à un webhook destiné à publier les fruits de la récolte de données dans un salon de discussion.
![](https://pads.jae.fi/uploads/upload_5b651f6db4e73bd2559f9913f8cb489d.png)
Toutes ces fonctions sont bien sûr obfusquées.

Dans une version antérieure du virus, celui-ci faisait aussi des appels vers une API localisée sur un domaine `f####.surf` ce qui pourrait indiquer la présence d'un RAT (Remote Administration Tool) dans certaines versions de celui-ci (voir section 3.3.2).

La version analysée du virus permet entre autre de voler les données suivantes:
- Codes de récupération de l'A2F (si l'utilisateur se reconnecte avec un client compromis ayant la fonctionalité de vol de mot de passe)
- Amis avec des badges "rares" (par exemple Early Supporter)
- Détails de paiement
- Détails de connection (token, nom d'utilisateur, email, numéro de téléphone, mot de passe quand la victime se reconnecte)

##### 3.3.2.2 La partie en dehors de Discord

Certaines versions de ce virus ne se limitent pas qu'à une injection dans Discord mais tentent de récolter plus d'informations sur l'ensemble de la machine compromise.
Comme évoqué dans la section 3.3.2.1, ces versions tentent de faire des appels à une API localisée sur un domaine externe a Discord.
Quelques possibles fonctionalitées de ces virus pourraient être:
 - Voler les cookies des navigateurs
 - Voler les mots de passe des navigateurs
 - Voler le token d'authentification du lanceur Minecraft™
 - Voler les mots de passe et identifiants d'un réseau WiFi™
 - Prendre des captures d'écran de la machine compromise

Il est a noter que l'analyse de ce virus n'est pas encore complète de notre côté. Il est donc possible que ce virus en fasse plus que prévu.

## 4 Mitigations

Afin d'éviter au maximum ce type d'attaque, il y a plusieurs recommendations.
1. Ne **jamais** cliquer sur des liens envoyés par des inconnus (et dans une certaine mesure, même vos ami·e·s)
2. Avoir l'antivirus Windows Defender d'activé (celui-ci suffit en général)
3. Ne jamais éxécuter un fichier provenant d'une source douteuse (exemple : site Web tiers, messages privés Discord)

Il est aussi recommandé de scanner son système au moins une fois par semaine avec votre antivirus.
Sous Linux ou macOS, [ClamAV](https://www.clamav.net/) peut être utilisé pour obtenir ce résultat (même si ces plateformes n'ont pas l'air d'être visées en ce moment même).

Afin de sécuriser vos comptes, il est aussi recommandé d'utiliser un gestionnaire de mots de passe tel que [Bitwarden](https://bitwarden.com/) afin d'avoir un mot de passe par site web et pour pouvoir les renouveler plus facilement.
Il vous faut aussi activer l'authentification a deux facteurs dès que possible.

## 5 Fin

Étant donné l'état actuel de l'écosystème Discord, il est a prévoir que la fréquence de ce type d'attaque ne fasse qu'augmenter.
Il est donc très important que les utilisateurs (vous) prennent conscience du problème.
Tout le monde est à la merci de ce type d'attaques, la version 1 du virus a été transmise par un autre développeur ayant une hygiène numérique correcte, il vous faut donc redoubler de vigilance.

Quand il est des attanquants, il semble que ce soit un public très jeune (de 13 à 15 ans) achetant ces programmes à des personnes plus éxpérimentées.
Pour ce qu'il est des motifs, nous pouvont spéculer que certains ne font cela que pour "jouer" et d'autres pour trouver des comptes "rares" à revendre.

L'analyse de ces virus n'êtant qu'a ses débuts, ce document sera mis à jour plus tard.

Ce document a été rédigé par Jae Lo Presti `@me:jae.fi` support et discussions le [canal de discussion Matrix](https://matrix.to/#/#home:jae.fi).
Merci a Minteck pour la relecture et correction.
