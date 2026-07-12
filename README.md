# WiiUStream PC Client v0.5.0 — 480p Turbo

Client Windows pour le plugin Aroma `StreamingPluginWiiU-Aroma-v0.5.0-480p-turbo`.

## Fonctions

- protocole UDP v2 compatible avec le plugin v0.5.0 ;
- réception par `recvfrom_into` sans allocation de datagramme ;
- buffers JPEG réutilisés ;
- une seule image compressée et une seule image décodée en attente ;
- suppression immédiate des images anciennes ;
- décodage JPEG dans un thread séparé ;
- affichage 854 × 480, redimensionnement rapide et plein écran ;
- statistiques de réception, affichage, débit, pertes et retard évité ;
- mémorisation de l’adresse IP.

## Utilisation

1. Installer `WiiUStream.wps` v0.5.0 dans Aroma.
2. Mettre le PC et la Wii U sur le même réseau local.
3. Autoriser l’application dans le pare-feu Windows pour les réseaux privés.
4. Saisir l’IPv4 de la Wii U puis cliquer sur **Connexion**.

Le programme écoute la vidéo sur UDP `9445` et envoie le signal de présence à UDP `9444`.

## Raccourcis

- `F11` ou `Alt + Entrée` : plein écran ;
- `Échap` : quitter le plein écran ;
- double-clic sur l’image : plein écran.

## Compilation locale

Lancer `build_windows.bat`. L’exécutable sera créé dans :

```text
dist/WiiUStream-PC-480p-Turbo.exe
```
