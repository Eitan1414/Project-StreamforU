# Wii U Stream — client Android

Client Android natif pour le protocole **Wii U Stream v1** du plugin Aroma modernisé.

## Fonctions

- saisie et mémorisation de l’adresse IPv4 de la Wii U ;
- envoi d’un paquet HELLO chaque seconde vers `UDP 9444` ;
- réception des fragments JPEG sur `UDP 9445` ;
- reconstruction des images par numéro de trame ;
- vérification de la taille et du CRC32 ;
- suppression des images incomplètes ;
- priorité donnée à l’image la plus récente pour réduire la latence ;
- affichage GamePad ou TV en conservant les proportions ;
- affichage des FPS, du débit et des pertes ;
- passage en paysage dès la première image ;
- toucher l’image pour masquer ou réafficher l’interface.

## Utilisation

1. Installer et activer `WiiUStream.wps` dans Aroma. (lien trouvable dans les realeses)
2. Mettre la Wii U et le téléphone sur le même réseau Wi-Fi.
3. Relever l’adresse IP locale de la Wii U.
4. Installer puis ouvrir l’APK.
5. Saisir l’adresse IP et appuyer sur **Connexion**.

Le plugin écoute les paquets de présence sur le port UDP `9444`. L’application reçoit les images sur le port UDP `9445`.

## Compilation du ZIP dans GitHub

Lorsque le projet reste sous forme de ZIP dans le dépôt, utiliser le workflow séparé `build-android-from-zip.yml` :

1. placer `WiiUStream-Android-Client-v0.1.0-alpha.zip` à la racine du dépôt ;
2. placer le workflow dans `.github/workflows/build-android-from-zip.yml` ;
3. ouvrir **Actions** puis lancer **Build Android client from ZIP** ;
4. télécharger l’artifact `WiiUStream-Android-debug` ;
5. installer `WiiUStream-Android-debug.apk`.

## Compilation d’un dépôt déjà décompressé

Le workflow intégré `.github/workflows/build-apk.yml` peut compiler directement le projet lorsqu’il est décompressé dans le dépôt.

## Configuration technique

- Android 8.0 minimum (`minSdk 26`) ;
- `compileSdk 36` et `targetSdk 36` ;
- JDK 17 ;
- Android Gradle Plugin 9.2.1 ;
- Gradle 9.4.1 ;
- aucune bibliothèque Android externe.

## Limites de cette alpha

- vidéo uniquement, sans audio ;
- une seule application cliente à la fois ;
- adresse IP saisie manuellement ;
- aucun chiffrement, usage réservé au réseau local de confiance ;
- les paquets UDP perdus ne sont pas retransmis afin de conserver une latence basse.
