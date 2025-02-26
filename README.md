# Nuxt.js auf Profihost

Diese Dokumentation führt dich durch den Prozess der Installation und Konfiguration einer Nuxt.js-Anwendung auf einem Profihost-Server. Folge den Schritten in den einzelnen Abschnitten, um eine vollständig funktionsfähige Nuxt-Anwendung zu erstellen und als Dienst zu betreiben.

## Inhaltsverzeichnis

1. [Node Version Manager (NVM) installieren](#1-node-version-manager-nvm-installieren)
2. [Nuxt-Projekt erstellen und konfigurieren](#2-nuxt-projekt-erstellen-und-konfigurieren)
3. [Service Daemon bei Profihost einrichten](#3-service-daemon-bei-profihost-einrichten)
4. [.htaccess als Reverse Proxy konfigurieren](#4-htaccess-als-reverse-proxy-konfigurieren)
5. [Wichtige Hinweise](#wichtige-hinweise)
6. [Weitere Ressourcen](#weitere-ressourcen)

## 1. Node Version Manager (NVM) installieren

NVM ermöglicht dir, verschiedene Node.js-Versionen zu verwalten und zwischen ihnen zu wechseln. Dies ist besonders nützlich, wenn du mehrere Projekte mit unterschiedlichen Node.js-Versionsanforderungen hast.

```bash
# Installiere NVM
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.5/install.sh | bash

# Lade die Umgebungsvariablen neu
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"

# Überprüfe die Installation
nvm --version

# Installiere die neueste stabile Node.js-Version
nvm install --lts

# Überprüfe die Node.js-Installation
node --version
npm --version
```

Nach der Installation kannst du jederzeit zwischen verschiedenen Node.js-Versionen wechseln. Für Nuxt.js empfehlen wir mindestens Node.js 16.x oder höher.

## 2. Nuxt-Projekt erstellen und konfigurieren

Erstelle ein neues Nuxt-Projekt mit dem offiziellen Nuxt-CLI-Tool. Du kannst die Standard-Template-Einstellungen verwenden oder dein Projekt individuell konfigurieren.

```bash
# Wechsle in das gewünschte Verzeichnis
cd ~/

# Erstelle ein neues Nuxt-Projekt
npx nuxi@latest init mein-nuxt-projekt

# Wechsle in das Projektverzeichnis
cd mein-nuxt-projekt

# Installiere Abhängigkeiten
npm install

# Erstelle ein Produktions-Build
npm run build

# Teste die Anwendung lokal
npm run preview
```

## 3. Service Daemon bei Profihost einrichten

Um deine Nuxt-Anwendung dauerhaft laufen zu lassen, kannst du bei Profihost einen Service Daemon einrichten. Dazu musst du eine Daemon-Konfigurationsdatei erstellen und beim Hosting-Panel hochladen.

```bash
# Lade eine vorkonfigurierte Daemon-Datei herunter
wget https://raw.githubusercontent.com/haupt-pascal/profihost-nuxt/main/daemon.sh
chmod +x daemon.sh
```

Nach dem Erstellen der Daemon-Konfigurationsdatei:

1. Logge dich in dein Profihost Kundencenter ein
2. Navigiere zu deinem Server
3. Suche nach der Option "Daemon" oder "Service Daemon"
4. Lade die erstellte daemon.sh Datei auf den Speicherplatz
5. Passe die Pfade innerhalb des Scripts an
6. Hinterlege als Befehl / Script den Pfad zum Script
7. Aktiviere den Daemon

Dein Nuxt-Dienst sollte nun automatisch starten und im Falle eines Absturzes neu gestartet werden.

## 4. .htaccess als Reverse Proxy konfigurieren

Um deinen Nuxt-Server über deine Domain erreichbar zu machen, kannst du Apache's mod_proxy mit einer .htaccess-Datei als Reverse Proxy konfigurieren.

```bash
# Erstelle eine .htaccess-Datei im Hauptverzeichnis deiner Website
cat > .htaccess << 'EOL'
DirectoryIndex disabled

RewriteEngine On

#RewriteCond %{REQUEST_FILENAME} !-d
#RewriteCond %{REQUEST_FILENAME} !-f

RewriteRule (.*) http://DAEMON_IP_ADDRESS:3000/$1 [P,L]
EOL

# Alternativ: Lade eine vorkonfigurierte .htaccess-Datei herunter
wget -O .htaccess https://raw.githubusercontent.com/haupt-pascal/profihost-nuxt/main/.htaccess
```

Die .htaccess-Datei leitet alle Anfragen an deine Domain an den lokalen Nuxt-Server weiter, der auf Port 3000 läuft. Dadurch kannst du deine Nuxt-Anwendung über deine normale Domain aufrufen, ohne den Port angeben zu müssen.

## Wichtige Hinweise

- Passe den Port (3000) an, falls du einen anderen Port in deiner Daemon-Konfiguration verwendest
- Solltest du auf Fehler stoßen, hilft dir der Support unter support@profihost.com gerne weiter

## Weitere Ressourcen

- [Nuxt Dokumentation](https://nuxt.com/docs) - Offizielle Nuxt-Dokumentation für detaillierte Informationen zu allen Features
- [GitHub Repository](https://github.com/haupt-pascal/profihost-nuxt) - Beispiel-Repository mit zusätzlichen Konfigurationsbeispielen für Profihost

---

© 2025 Nuxt - MIT License