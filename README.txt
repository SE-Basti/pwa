TRAININGS-BAUKASTEN – PWA (installierbare Web-App)
===================================================

INHALT
  index.html              – die App
  manifest.webmanifest    – App-Manifest (Name, Icons, Farben)
  sw.js                   – Service Worker (Offline-Betrieb)
  icons/                  – App-Icons (192, 512, maskable, Apple)

WICHTIG
  Eine PWA braucht HTTPS (oder localhost). Per Doppelklick als
  file:// funktioniert der Service Worker NICHT – dann läuft die App
  zwar, ist aber nicht installierbar/offline. Also hosten:

HOSTEN AUF GITHUB PAGES (wie dein Zeit-Terminal)
  1. Neues Repo anlegen, den GESAMTEN Ordnerinhalt hochladen
     (index.html, manifest.webmanifest, sw.js und den Ordner icons/).
  2. Settings -> Pages -> Branch: main, Ordner: / (root) -> Save.
  3. Die Seite ist dann unter
     https://<dein-name>.github.io/<repo>/ erreichbar.
  Hinweis: Alle Pfade sind relativ ("./"), funktioniert also auch im
  Unterordner einer Pages-Site.

INSTALLIEREN
  Android/Chrome: Beim Öffnen erscheint oben der Button
    "⤓ Als App installieren" (oder Menü -> "App installieren").
  iPhone/Safari:  Teilen-Symbol -> "Zum Home-Bildschirm".
  Desktop/Chrome: Installations-Symbol in der Adressleiste.

OFFLINE
  Nach dem ersten Online-Laden werden App, Schriftarten und Icons
  gecacht – danach läuft alles offline. Deine Setups und der
  Trainingsverlauf liegen lokal auf dem Gerät (localStorage).

UPDATES
  Wenn du index.html änderst, in sw.js die Zeile
    const CACHE = "tb-v1";
  auf "tb-v2" usw. erhöhen – dann lädt die App die neue Version.
