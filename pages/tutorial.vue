<style lang="scss">
/*linear gradients */
@media (prefers-color-scheme: light) {
  .tutorial-gradient-border {
    background: linear-gradient(to right, #ffffff, #ffffff), linear-gradient(to right, #00DC82, #1DE0B1, #36E4DA);
  }
  .tutorial-section-border {
    background: linear-gradient(var(--gradient-angle), rgba(0, 220, 130), rgba(0, 220, 130, 0.6), rgba(255, 255, 255, 0.8), rgba(0, 220, 130));
  }
  .code-block {
    background-color: #f1f5f9;
    color: #1e293b;
  }
}

@media (prefers-color-scheme: dark) {
  .tutorial-gradient-border {
    background: linear-gradient(to right, #18181B, #18181B), linear-gradient(to right, #00DC82, #1DE0B1, #36E4DA);
  }
  .tutorial-section-border {
    background: linear-gradient(var(--gradient-angle), rgba(0, 220, 130), rgba(0, 63, 37), rgba(255, 255, 255, 0.2), rgba(0, 63, 37));
  }
  .code-block {
    background-color: #1e293b;
    color: #f8fafc;
  }
}

.tutorial-gradient-border {
  background-clip: padding-box, border-box;
  background-origin: padding-box, border-box;
  border-color: transparent;
  border-radius: 12px;
  border-width: 1px;
}

.tutorial-gradient-border:hover > :is(.tutorial-gradient-left, .tutorial-gradient-right) {
  opacity: 0.2;
}

.tutorial-gradient-left, .tutorial-gradient-right {
  opacity: 0;
}

.tutorial-section {
  position: relative;
  border: 1px solid transparent;
  border-radius: 12px;
  overflow: hidden;
}

.tutorial-section:hover > .gradient-border {
  opacity: 1;
  animation: gradient-rotate 5s cubic-bezier(0,0,1,1) 0s infinite reverse;
  transition: all 0.3s linear;
}

.gradient-border {
  opacity: 0;
  position: absolute;
  top: 0;
  left: 0;
  width: calc(100% + 2px);
  height: calc(100% + 2px);
  border-radius: 12px;
  z-index: -1;
  transform: translate(-1px, -1px);
}

.code-block {
  border-radius: 8px;
  padding: 1rem;
  font-family: monospace;
  white-space: pre-wrap;
  overflow-x: auto;
}

.copy-button {
  position: absolute;
  top: 0.5rem;
  right: 0.5rem;
  background-color: rgba(255, 255, 255, 0.1);
  border-radius: 4px;
  padding: 0.25rem 0.5rem;
  font-size: 0.75rem;
  cursor: pointer;
  transition: background-color 0.2s;
}

.copy-button:hover {
  background-color: rgba(255, 255, 255, 0.2);
}

@property --gradient-angle {
  syntax: '<angle>';
  inherits: false;
  initial-value: 180deg;
}

@keyframes gradient-rotate {
  0% {
    --gradient-angle: 0deg;
  }

  100% {
    --gradient-angle: 360deg;
  }
}
</style>

<template>
    <div
        class="antialiased bg-black text-white min-h-screen place-content-center flex flex-col items-center justify-center text-sm sm:text-base"
    >
        <div class="flex-1 flex flex-col gap-y-8 py-8 w-full max-w-5xl px-4">
            <div class="flex flex-col gap-y-4 items-center justify-center">
                <a href="https://nuxt.com" target="_blank">
                    <svg
                        width="61"
                        height="42"
                        viewBox="0 0 61 42"
                        fill="none"
                        xmlns="http://www.w3.org/2000/svg"
                    >
                        <path
                            d="M33.9869 41.2211H56.412C57.1243 41.2212 57.824 41.0336 58.4408 40.6772C59.0576 40.3209 59.5698 39.8083 59.9258 39.191C60.2818 38.5737 60.469 37.8736 60.4687 37.1609C60.4684 36.4482 60.2805 35.7482 59.924 35.1313L44.864 9.03129C44.508 8.41416 43.996 7.90168 43.3793 7.54537C42.7626 7.18906 42.063 7.00147 41.3509 7.00147C40.6387 7.00147 39.9391 7.18906 39.3225 7.54537C38.7058 7.90168 38.1937 8.41416 37.8377 9.03129L33.9869 15.7093L26.458 2.65061C26.1018 2.03354 25.5895 1.52113 24.9726 1.16489C24.3557 0.808639 23.656 0.621094 22.9438 0.621094C22.2316 0.621094 21.5318 0.808639 20.915 1.16489C20.2981 1.52113 19.7858 2.03354 19.4296 2.65061L0.689224 35.1313C0.332704 35.7482 0.144842 36.4482 0.144532 37.1609C0.144222 37.8736 0.331476 38.5737 0.687459 39.191C1.04344 39.8083 1.5556 40.3209 2.17243 40.6772C2.78925 41.0336 3.48899 41.2212 4.20126 41.2211H18.2778C23.8551 41.2211 27.9682 38.7699 30.7984 33.9876L37.6694 22.0813L41.3498 15.7093L52.3951 34.8492H37.6694L33.9869 41.2211ZM18.0484 34.8426L8.2247 34.8404L22.9504 9.32211L30.2979 22.0813L25.3784 30.6092C23.4989 33.7121 21.3637 34.8426 18.0484 34.8426Z"
                            fill="#00DC82"
                        />
                    </svg>
                </a>
                <h1
                    class="text-white text-4xl sm:text-5xl font-semibold text-center"
                >
                    Nuxt Tutorial für Profihost
                </h1>
            </div>

            <!-- Main Tutorial Content -->
            <div class="relative tutorial-gradient-border mb-8">
                <div
                    class="tutorial-gradient-left absolute left-0 inset-y-0 w-[20%] bg-gradient-to-r to-transparent from-green-400 rounded-xl z-1 transition-opacity duration-300"
                ></div>
                <div
                    class="tutorial-gradient-right absolute right-0 inset-y-0 w-[20%] bg-gradient-to-l to-transparent from-blue-400 rounded-xl z-1 transition-opacity duration-300"
                ></div>
                <div class="flex flex-col rounded-xl px-6 py-6 z-10">
                    <p class="mb-6">
                        Diese Anleitung führt dich durch den Prozess der
                        Installation und Konfiguration einer Nuxt-Anwendung auf
                        einem Profihost-Server. Folge den Schritten in den
                        einzelnen Abschnitten, um eine vollständig
                        funktionsfähige Nuxt-Anwendung zu erstellen und als
                        Dienst zu betreiben.
                    </p>
                    <div class="flex flex-col gap-y-6">
                        <!-- Section 1: NVM Installation -->
                        <section class="tutorial-section bg-gray-900">
                            <div
                                class="gradient-border tutorial-section-border"
                            ></div>
                            <div class="p-6">
                                <h3 class="font-semibold text-xl mb-4">
                                    1. Node Version Manager (NVM) installieren
                                </h3>
                                <p class="mb-4">
                                    NVM ermöglicht dir, verschiedene
                                    Node.js-Versionen zu verwalten und zwischen
                                    ihnen zu wechseln. Dies ist besonders
                                    nützlich, wenn du mehrere Projekte mit
                                    unterschiedlichen
                                    Node.js-Versionsanforderungen hast.
                                </p>
                                <div class="relative">
                                    <div class="code-block mb-4">
# Installiere NVM <br>
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.5/install.sh | bash
<br> <br>
# Lade die Umgebungsvariablen neu <br>
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"
<br> <br>
# Überprüfe die Installation <br>
nvm --version
<br> <br>
# Installiere die neueste stabile Node.js-Version <br>
nvm install --lts
<br> <br>
# Überprüfe die Node.js-Installation
node --version<br>
npm --version</div>
                                    <button
                                        class="copy-button"
                                        @click="copyToClipboard('nvm-install')"
                                    >
                                        Kopieren
                                    </button>
                                </div>
                                <p class="mt-4">
                                    Nach der Installation kannst du jederzeit
                                    zwischen verschiedenen Node.js-Versionen
                                    wechseln. Für Nuxt.js empfehlen wir
                                    mindestens Node.js 16.x oder höher.
                                </p>
                            </div>
                        </section>

                        <!-- Section 2: Nuxt Setup -->
                        <section class="tutorial-section bg-gray-900">
                            <div
                                class="gradient-border tutorial-section-border"
                            ></div>
                            <div class="p-6">
                                <h3 class="font-semibold text-xl mb-4">
                                    2. Nuxt-Projekt erstellen und konfigurieren
                                </h3>
                                <p class="mb-4">
                                    Erstelle ein neues Nuxt-Projekt mit dem
                                    offiziellen Nuxt-CLI-Tool. Du kannst die
                                    Standard-Template-Einstellungen verwenden
                                    oder dein Projekt individuell konfigurieren.
                                </p>
                                <div class="relative">
                                    <div class="code-block mb-4">
# Wechsle in das gewünschte Verzeichnis <br>
cd ~/
<br> <br>
# Erstelle ein neues Nuxt-Projekt <br>
npx nuxi@latest init mein-nuxt-projekt
<br> <br>
# Wechsle in das Projektverzeichnis <br>
cd mein-nuxt-projekt
<br> <br>
# Installiere Abhängigkeiten <br>
npm install
<br> <br>
# Erstelle ein Produktions-Build <br>
npm run build
<br> <br>
# Teste die Anwendung lokal <br>
npm run preview</div>
                                    <button
                                        class="copy-button"
                                        @click="copyToClipboard('nuxt-setup')"
                                    >
                                        Kopieren
                                    </button>
                                </div>
                            </div>
                        </section>

                        <!-- Section 3: Service Daemon Setup -->
                        <section class="tutorial-section bg-gray-900">
                            <div
                                class="gradient-border tutorial-section-border"
                            ></div>
                            <div class="p-6">
                                <h3 class="font-semibold text-xl mb-4">
                                    3. Service Daemon bei Profihost einrichten
                                </h3>
                                <p class="mb-4">
                                    Um deine Nuxt-Anwendung dauerhaft laufen zu
                                    lassen, kannst du bei Profihost einen
                                    Service Daemon einrichten. Dazu musst du
                                    eine Daemon-Konfigurationsdatei erstellen
                                    und beim Hosting-Panel hochladen.
                                </p>
                                <div class="relative">
                                    <div class="code-block mb-4">
# Lade eine vorkonfigurierte Daemon-Datei herunter <br>
wget https://raw.githubusercontent.com/haupt-pascal/profihost-nuxt/main/daemon.sh
chmod +x daemon.sh
</div>
                                    <button
                                        class="copy-button"
                                        @click="copyToClipboard('daemon-setup')"
                                    >
                                        Kopieren
                                    </button>
                                </div>
                                <p class="mt-4 mb-2">
                                    Nach dem Erstellen der
                                    Daemon-Konfigurationsdatei:
                                </p>
                                <ol class="list-decimal ml-6 mb-4 space-y-2">
                                    <li>
                                        Logge dich in dein Profihost
                                        Kundencenter ein
                                    </li>
                                    <li>
                                        Navigiere zu deinem Server
                                    </li>
                                    <li>
                                        Suche nach der Option "Daemon" oder
                                        "Service Daemon"
                                    </li>
                                    <li>
                                        Lade die erstellte daemon.sh
                                        Datei auf den Speicherplatz
                                    </li>
                                    <li>
                                        Passe die Pfade innerhalb des Scripts an
                                    </li>
                                    <li>
                                        Hinterlege als Befehl / Script den
                                        Pfad zum Script
                                    </li>
                                    <li>Aktiviere den Daemon</li>
                                </ol>
                                <p>
                                    Dein Nuxt-Dienst sollte nun automatisch
                                    starten und im Falle eines Absturzes neu
                                    gestartet werden.
                                </p>
                            </div>
                        </section>

                        <!-- Section 4: .htaccess Reverse Proxy -->
                        <section class="tutorial-section bg-gray-900">
                            <div
                                class="gradient-border tutorial-section-border"
                            ></div>
                            <div class="p-6">
                                <h3 class="font-semibold text-xl mb-4">
                                    4. .htaccess als Reverse Proxy konfigurieren
                                </h3>
                                <p class="mb-4">
                                    Um deinen Nuxt-Server über deine Domain
                                    erreichbar zu machen, kannst du Apache's
                                    mod_proxy mit einer .htaccess-Datei als
                                    Reverse Proxy konfigurieren.
                                </p>
                                <div class="relative">
                                    <div class="code-block mb-4">
# Erstelle eine .htaccess-Datei im Hauptverzeichnis deiner Website <br>
cat > .htaccess << 'EOL' 
<br> <br>
# Füge folgenden Code in die .htaccess-Datei ein <br>
DirectoryIndex disabled
<br><br>
RewriteEngine On
<br><br>
#RewriteCond %{REQUEST_FILENAME} !-d
#RewriteCond %{REQUEST_FILENAME} !-f
<br><br>
RewriteRule (.*)  http://DAEMON_IP_ADDRESS:3000/$1 [P,L]
<br><br>
</div>
<div class="code-block mb-4">
    # Alternativ: Lade eine vorkonfigurierte .htaccess-Datei herunter <br>
wget -O .htaccess https://raw.githubusercontent.com/haupt-pascal/profihost-nuxt/main/.htaccess
</div>
                                    <button
                                        class="copy-button"
                                        @click="
                                            copyToClipboard('htaccess-setup')
                                        "
                                    >
                                        Kopieren
                                    </button>
                                </div>
                                <p class="mt-4">
                                    Die .htaccess-Datei leitet alle Anfragen an
                                    deine Domain an den lokalen Nuxt-Server
                                    weiter, der auf Port 3000 läuft. Dadurch
                                    kannst du deine Nuxt-Anwendung über deine
                                    normale Domain aufrufen, ohne den Port
                                    angeben zu müssen.
                                </p>
                                <div class="bg-yellow-700 p-4 rounded-lg mt-4">
                                    <h4 class="font-semibold">
                                        Wichtige Hinweise:
                                    </h4>
                                    <ul class="list-disc ml-6 mt-2">
                                        <li>
                                            Passe den Port (3000) an, falls du
                                            einen anderen Port in deiner
                                            Daemon-Konfiguration verwendest
                                        </li>
                                        <li>
                                            Solltest du auf Fehler stossen hilft dir der Support 
                                            unter support@profihost.com gerne weiter
                                        </li>
                                    </ul>
                                </div>
                            </div>
                        </section>
                    </div>
                </div>
            </div>

            <!-- Additional Resources -->
            <div class="text-center mb-8">
                <h3 class="font-semibold text-xl mb-4">Weitere Ressourcen</h3>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-4">
                    <a
                        href="https://nuxt.com/docs"
                        target="_blank"
                        class="bg-gray-900 p-4 rounded-xl hover:bg-gray-800 transition-colors"
                    >
                        <h4 class="font-semibold mb-2">Nuxt Dokumentation</h4>
                        <p class="text-gray-300">
                            Offizielle Nuxt-Dokumentation für detaillierte
                            Informationen zu allen Features
                        </p>
                    </a>
                    <a
                        href="https://github.com/haupt-pascal/profihost-nuxt"
                        target="_blank"
                        class="bg-gray-900 p-4 rounded-xl hover:bg-gray-800 transition-colors"
                    >
                        <h4 class="font-semibold mb-2">GitHub Repository</h4>
                        <p class="text-gray-300">
                            Beispiel-Repository mit zusätzlichen
                            Konfigurationsbeispielen für Profihost
                        </p>
                    </a>
                </div>
            </div>
        </div>

        <!-- Footer -->
        <footer
            class="relative border-t bg-black border-gray-900 w-full h-[70px] flex items-center"
        >
            <div
                class="absolute inset-x-0 flex items-center justify-center -top-3"
            >
                <a href="https://nuxt.com" target="_blank">
                    <svg
                        width="70"
                        height="20"
                        viewBox="0 0 70 20"
                        fill="none"
                        xmlns="http://www.w3.org/2000/svg"
                    >
                        <ellipse
                            cx="34.6528"
                            cy="10.4209"
                            rx="34.5"
                            ry="9.5"
                            fill="white"
                            class="hidden"
                        />
                        <ellipse
                            cx="34.6528"
                            cy="10.4209"
                            rx="34.5"
                            ry="9.5"
                            fill="black"
                            class="block"
                        />
                        <path
                            d="M36.0605 15.9209H42.6256C42.8341 15.9209 43.0389 15.8655 43.2195 15.7602C43.4001 15.6548 43.55 15.5033 43.6543 15.3209C43.7585 15.1384 43.8133 14.9315 43.8132 14.7208C43.8131 14.5102 43.7581 14.3033 43.6537 14.1209L39.2448 6.40667C39.1406 6.22427 38.9907 6.0728 38.8101 5.96748C38.6296 5.86217 38.4248 5.80672 38.2163 5.80672C38.0078 5.80672 37.803 5.86217 37.6225 5.96748C37.4419 6.0728 37.292 6.22427 37.1878 6.40667L36.0605 8.38048L33.8563 4.52076C33.752 4.33837 33.602 4.18692 33.4214 4.08163C33.2409 3.97633 33.036 3.9209 32.8275 3.9209C32.619 3.9209 32.4141 3.97633 32.2335 4.08163C32.053 4.18692 31.903 4.33837 31.7987 4.52076L26.3123 14.1209C26.2079 14.3033 26.1529 14.5102 26.1528 14.7208C26.1527 14.9315 26.2076 15.1384 26.3118 15.3209C26.416 15.5033 26.5659 15.6548 26.7465 15.7602C26.9271 15.8655 27.1319 15.9209 27.3405 15.9209H31.4615C33.0943 15.9209 34.2984 15.1964 35.127 13.7829L37.1385 10.2638L38.216 8.38048L41.4496 14.0376H37.1385L36.0605 15.9209ZM31.3943 14.0356L28.5184 14.035L32.8294 6.49263L34.9805 10.2638L33.5402 12.7844C32.99 13.7015 32.3649 14.0356 31.3943 14.0356Z"
                            fill="#00DC82"
                        />
                    </svg>
                </a>
            </div>

            <div class="mx-auto sm:px-6 lg:px-8 px-4 w-full">
                <div
                    class="flex flex-col items-center gap-3 sm:flex-row sm:justify-between"
                >
                    <div
                        class="flex flex-col-reverse items-center gap-3 sm:flex-row"
                    >
                        <span class="text-sm text-gray-300"
                            >© {{ new Date().getFullYear() }} Nuxt - MIT
                            License</span
                        >
                    </div>
                    <ul class="flex items-center justify-end gap-3">
                        <li>
                            <a
                                href="https://chat.nuxt.dev"
                                target="_blank"
                                class="focus-visible:ring-2 text-gray-300 hover:text-white"
                            >
                                <span class="sr-only">Nuxt Discord Server</span>
                                <svg
                                    width="16"
                                    height="12"
                                    viewBox="0 0 16 12"
                                    fill="none"
                                    xmlns="http://www.w3.org/2000/svg"
                                >
                                    <path
                                        d="M13.3705 1.07322C13.3663 1.06497 13.3594 1.05851 13.351 1.05499C12.3785 0.599487 11.3522 0.274675 10.2978 0.0886873C10.2882 0.0868693 10.2783 0.0881809 10.2695 0.0924354C10.2607 0.0966899 10.2534 0.103671 10.2487 0.112385C10.109 0.371315 9.98212 0.637279 9.86863 0.909263C8.73205 0.733138 7.57595 0.733138 6.43938 0.909263C6.32514 0.636589 6.19624 0.370559 6.05328 0.112385C6.04838 0.10386 6.04107 0.0970401 6.03232 0.0928132C6.02356 0.0885863 6.01377 0.0871486 6.0042 0.0886873C4.9497 0.274285 3.92333 0.599121 2.95092 1.05502C2.9426 1.05862 2.93558 1.06477 2.93082 1.07262C0.986197 4.03716 0.453491 6.92881 0.714819 9.78465C0.715554 9.79165 0.71766 9.79843 0.721013 9.80458C0.724365 9.81073 0.728896 9.81613 0.734334 9.82046C1.86667 10.6763 3.1332 11.3296 4.47988 11.7525C4.48937 11.7554 4.49949 11.7552 4.5089 11.7521C4.51831 11.7489 4.52655 11.7429 4.53251 11.7349C4.82175 11.3331 5.07803 10.9077 5.29876 10.4629C5.3018 10.4568 5.30353 10.4501 5.30384 10.4433C5.30416 10.4365 5.30305 10.4296 5.3006 10.4233C5.29814 10.4169 5.29439 10.4111 5.2896 10.4064C5.2848 10.4016 5.27906 10.3979 5.27277 10.3955C4.86862 10.2377 4.47736 10.0474 4.10266 9.82645C4.09586 9.82236 4.09014 9.81663 4.08602 9.80976C4.0819 9.80288 4.0795 9.79508 4.07903 9.78703C4.07856 9.77899 4.08004 9.77095 4.08334 9.76362C4.08664 9.7563 4.09166 9.74992 4.09794 9.74504C4.17657 9.4.17657 9.68491 4.25524 9.62236 4.33032 9.55918C4.33699 9.55358 4.34506 9.54998 4.35362 9.5488C4.36218 9.54762 4.3709 9.54891 4.37879 9.55252C6.83362 10.6962 9.4913 10.6962 11.9171 9.55252C11.925 9.54868 11.9338 9.54721 11.9425 9.54829C11.9512 9.54936 11.9594 9.55293 11.9662 9.55858C12.0413 9.62176 12.1199 9.68491 12.1991 9.74504C12.2054 9.74987 12.2105 9.75621 12.2138 9.7635C12.2172 9.7708 12.2187 9.77882 12.2183 9.78687C12.2179 9.79492 12.2156 9.80274 12.2115 9.80964C12.2074 9.81654 12.2018 9.82232 12.195 9.82645C11.8211 10.0492 11.4295 10.2394 11.0243 10.3949C11.018 10.3974 11.0123 10.4012 11.0075 10.406C11.0028 10.4109 10.9991 10.4167 10.9967 10.4231C10.9943 10.4295 10.9932 10.4364 10.9936 10.4433C10.9939 10.4501 10.9957 10.4568 10.9988 10.4629C11.2232 10.9052 11.4791 11.3301 11.7645 11.7342C11.7703 11.7425 11.7785 11.7487 11.7879 11.7519C11.7974 11.7552 11.8076 11.7554 11.8171 11.7524C13.1662 11.331 14.4349 10.6776 15.5687 9.82046C15.5742 9.81635 15.5788 9.81108 15.5822 9.80501C15.5855 9.79893 15.5876 9.7922 15.5882 9.78525C15.9011 6.4836 15.0644 3.61565 13.3705 1.07322ZM5.66537 8.04574C4.92629 8.04574 4.31731 7.35337 4.31731 6.50305C4.31731 5.65274 4.91448 4.96032 5.66537 4.96032C6.42213 4.96032 7.02522 5.65875 7.01341 6.503C7.01341 7.35337 6.41622 8.04574 5.66537 8.04574ZM10.6496 8.04574C9.91051 8.04574 9.30153 7.35337 9.30153 6.50305C9.30153 5.65274 9.8987 4.96032 10.6496 4.96032C11.4064 4.96032 12.0094 5.65875 11.9976 6.503C11.9976 7.35337 11.4064 8.04574 10.6496 8.04574Z"
                                    </path>
                                </svg>
                            </a>
                        </li>
                    </ul>
                </div>
            </div>
        </footer>
    </div>
</template>
<script>
export default {
    methods: {
        copyToClipboard(id) {
            const codeBlocks = {
                'nvm-install': `# Installiere NVM
wget -qO- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.5/install.sh | bash

# Lade die Umgebungsvariablen neu
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \\. "$NVM_DIR/nvm.sh"
[ -s "$NVM_DIR/bash_completion" ] && \\. "$NVM_DIR/bash_completion"

# Überprüfe die Installation
nvm --version

# Installiere die neueste stabile Node.js-Version
nvm install --lts

# Überprüfe die Node.js-Installation
node --version
npm --version`,
                'nuxt-setup': `# Wechsle in das gewünschte Verzeichnis
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
npm run preview`,
                'nuxt-config': `// nuxt.config.ts
export default defineNuxtConfig({
  // Aktiviere SSR-Modus
  ssr: true,
  
  // Setze den Host auf 0.0.0.0, um auf alle Netzwerkschnittstellen zu hören
  devServer: {
    host: '0.0.0.0'
  },
  
  // Optional: Konfiguriere einen Proxy für API-Anfragen
  nitro: {
    preset: 'node-server',
    // Weitere Nitro-Optionen hier...
  },
  
  // Weitere Konfigurationen...
})`,
                'daemon-setup': `# Erstelle eine Service Daemon Konfigurationsdatei
cat > nuxt-daemon.json << 'EOL'
{
  "apps": [
    {
      "name": "nuxt-app",
      "cwd": "/home/dein-benutzername/mein-nuxt-projekt",
      "script": "node",
      "args": ".output/server/index.mjs",
      "exec_mode": "fork",
      "instances": 1,
      "autorestart": true,
      "max_memory_restart": "1G",
      "env": {
        "HOST": "127.0.0.1",
        "PORT": "3000",
        "NODE_ENV": "production"
      }
    }
  ]
}
EOL

# Lade eine vorkonfigurierte Daemon-Datei herunter (Alternative)
wget -O nuxt-daemon.json https://raw.githubusercontent.com/haupt-pascal/profihost-nuxt/main/daemon.json`,
                'htaccess-setup': `# Erstelle eine .htaccess-Datei im Hauptverzeichnis deiner Website
cat > .htaccess << 'EOL'
# Aktiviere den Rewrite-Engine
RewriteEngine On

# Stelle sicher, dass die Anfrage nicht bereits an die Backend-Anwendung gerichtet ist
RewriteCond %{HTTP:Connection} Upgrade [NC]
RewriteCond %{HTTP:Upgrade} websocket [NC]
RewriteRule /(.*) ws://127.0.0.1:3000/$1 [P,L]

# Leite alle Anfragen an den Nuxt-Server weiter
RewriteRule ^(.*)$ http://127.0.0.1:3000/$1 [P,L]

# Set Headers
Header set Access-Control-Allow-Origin "*"

# Konfiguriere Proxy-Timeout (optional)
ProxyTimeout 600

# Aktiviere X-Forwarded-For (optional)
ProxyPreserveHost On
EOL

# Alternativ: Lade eine vorkonfigurierte .htaccess-Datei herunter
wget -O .htaccess https://raw.githubusercontent.com/haupt-pascal/profihost-nuxt/main/.htaccess`,
            };
            
            // Kopiere den Code in die Zwischenablage
            if (codeBlocks[id]) {
                navigator.clipboard
                    .writeText(codeBlocks[id])
                    .then(() => {
                        // Erfolgsmeldung hier einfügen, falls gewünscht
                        const buttons =
                            document.querySelectorAll('.copy-button');
                        buttons.forEach((button) => {
                            button.textContent = 'Kopieren';
                        });
                        
                        const clickedButton = document.querySelector(
                            `button[onclick="copyToClipboard('${id}')"]`
                        );
                        if (clickedButton) {
                            clickedButton.textContent = 'Kopiert!';
                            setTimeout(() => {
                                clickedButton.textContent = 'Kopieren';
                            }, 2000);
                        }
                    })
                    .catch((err) => {
                        console.error(
                            'Fehler beim Kopieren in die Zwischenablage:',
                            err
                        );
                    });
            }
        },
    },
};
</script>