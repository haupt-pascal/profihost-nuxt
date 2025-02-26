<style lang="scss">
/*linear gradients */
@media (prefers-color-scheme: light) {
  .get-started-gradient-border {
    background: linear-gradient(to right, #ffffff, #ffffff), linear-gradient(to right, #00DC82, #1DE0B1, #36E4DA);
  }
  .gradient-border-modules {
    background: linear-gradient(var(--gradient-angle), rgba(247, 209, 76), rgba(247, 209, 76, 0.6), rgba(255, 255, 255, 0.8), rgba(247, 209, 76));
  }
  .gradient-border-examples {
    background: linear-gradient(var(--gradient-angle), rgba(141, 234, 255), rgba(141, 234, 255, 0.6), rgba(255, 255, 255, 0.8), rgba(141, 234, 255));
  }
  .gradient-border-documentation {
    background: linear-gradient(var(--gradient-angle), rgba(0, 220, 130), rgba(0, 220, 130, 0.6), rgba(255, 255, 255, 0.8), rgba(0, 220, 130));
  }
}

@media (prefers-color-scheme: dark) {
  .get-started-gradient-border {
    background: linear-gradient(to right, #18181B, #18181B), linear-gradient(to right, #00DC82, #1DE0B1, #36E4DA);
  }
  .gradient-border-modules {
    background: linear-gradient(var(--gradient-angle), rgba(247, 209, 76), rgba(163, 129, 8), rgba(255, 255, 255, 0.3), rgba(163, 129, 8));
  }
  .gradient-border-examples {
    background: linear-gradient(var(--gradient-angle), rgba(141, 234, 255), rgba(0, 138, 169), rgba(255, 255, 255, 0.3), rgba(0, 138, 169));
  }
  .gradient-border-documentation {
    background: linear-gradient(var(--gradient-angle), rgba(0, 220, 130), rgba(0, 63, 37), rgba(255, 255, 255, 0.2), rgba(0, 63, 37));
  }
}

/* get started */
.get-started-gradient-border {
  background-clip: padding-box, border-box;
  background-origin: padding-box, border-box;
  border-color: transparent;
  border-radius: 12px;
  border-width: 1px;
}

.get-started-gradient-border:hover > :is(.get-started-gradient-left, .get-started-gradient-right) {
  opacity: 0.2;
}

.get-started-gradient-left, .get-started-gradient-right {
  opacity: 0;
}

/* gradient border */
.gradient-border {
  opacity: 0;
  position: absolute;
  top: 0;
  left: 0;
  width: calc(100% + 2px);
  border-radius: 12px;
  z-index: -1;
  transform: translate(-1px, -1px);
}

.gradient-border-rect {
  height: calc(100% + 2px);
}

@media (min-width: 1024px) {
  .gradient-border-rect {
    height: calc(100% + 1px);
  }
}

.gradient-border-square {
  height: calc(100% + 2px);
}

.modules-gradient-right {
  opacity: 0;
}

.modules-container:hover > .gradient-border, .examples-container:hover > .gradient-border, .documentation-container:hover > .gradient-border {
  opacity: 1;
  animation: gradient-rotate 5s cubic-bezier(0,0,1,1) 0s infinite reverse;
  transition: all 0.3s linear;
}

.modules-container:hover > .modules-gradient-right {
  opacity: 0.2;
}

.examples-container:hover > .examples-gradient-right {
  opacity: 0.2;
}

.examples-gradient-right {
  opacity: 0;
}

/* images */
.documentation-image-color-light, .documentation-image-color-dark {
  display: none;
}

.modules-image-color-light, .modules-image-color-dark {
  display: none;
}

.examples-image-color-light, .examples-image-color-dark {
  display: none;
}

/* image */
@media (prefers-color-scheme: light) {
  /*modules*/
  .modules-image-light {
    display: block;
  }
  .modules-image-dark {
    display: none;
  }
  .modules-container:hover > a > .modules-image-light {
    display: none;
  }
  .modules-container:hover > a > .modules-image-color-light {
    display: block;
  }
  /* examples */
  .examples-image-light {
    display: block;
  }
  .examples-image-dark {
    display: none;
  }
  .examples-container:hover > a > .examples-image-light {
    display: none;
  }
  .examples-container:hover > a > .examples-image-color-light {
    display: block;
  }
  /* documentation */
  .documentation-image-light {
    display: block;
  }
  .documentation-image-dark {
    display: none;
  }
  .documentation-container:hover > a > div > .documentation-image-light {
    display: none;
  }
  .documentation-container:hover > a > div > .documentation-image-color-light {
    display: block;
  }
}

@media (prefers-color-scheme: dark) {
  /*modules*/
  .modules-image-dark {
    display: block;
  }
  .modules-image-light {
    display: none;
  }
  .modules-container:hover > a > .modules-image-color-dark {
    display: block;
  }
  .modules-container:hover > a > .modules-image-dark {
    display: none;
  }
  /* examples */
  .examples-image-dark {
    display: block;
  }
  .examples-image-light {
    display: none;
  }
  .examples-container:hover > a > .examples-image-color-dark {
    display: block;
  }
  .examples-container:hover > a > .examples-image-dark {
    display: none;
  }
  /* documentation */
  .documentation-image-dark {
    display: block;
  }
  .documentation-image-light {
    display: none;
  }
  .documentation-container:hover > a > div >.documentation-image-color-dark {
    display: block;
  }
  .documentation-container:hover > a > div > .documentation-image-dark {
    display: none;
  }
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
      <div class="antialiased bg-black text-white min-h-screen place-content-center flex flex-col items-center justify-center text-sm sm:text-base">
    <div class="flex-1 flex flex-col gap-y-16 py-14">
      <div class="flex flex-col gap-y-4 items-center justify-center">
        <a href="https://nuxt.com" target="_blank">
          <svg width="61" height="42" viewBox="0 0 61 42" fill="none" xmlns="http://www.w3.org/2000/svg">
            <path d="M33.9869 41.2211H56.412C57.1243 41.2212 57.824 41.0336 58.4408 40.6772C59.0576 40.3209 59.5698 39.8083 59.9258 39.191C60.2818 38.5737 60.469 37.8736 60.4687 37.1609C60.4684 36.4482 60.2805 35.7482 59.924 35.1313L44.864 9.03129C44.508 8.41416 43.996 7.90168 43.3793 7.54537C42.7626 7.18906 42.063 7.00147 41.3509 7.00147C40.6387 7.00147 39.9391 7.18906 39.3225 7.54537C38.7058 7.90168 38.1937 8.41416 37.8377 9.03129L33.9869 15.7093L26.458 2.65061C26.1018 2.03354 25.5895 1.52113 24.9726 1.16489C24.3557 0.808639 23.656 0.621094 22.9438 0.621094C22.2316 0.621094 21.5318 0.808639 20.915 1.16489C20.2981 1.52113 19.7858 2.03354 19.4296 2.65061L0.689224 35.1313C0.332704 35.7482 0.144842 36.4482 0.144532 37.1609C0.144222 37.8736 0.331476 38.5737 0.687459 39.191C1.04344 39.8083 1.5556 40.3209 2.17243 40.6772C2.78925 41.0336 3.48899 41.2212 4.20126 41.2211H18.2778C23.8551 41.2211 27.9682 38.7699 30.7984 33.9876L37.6694 22.0813L41.3498 15.7093L52.3951 34.8492H37.6694L33.9869 41.2211ZM18.0484 34.8426L8.2247 34.8404L22.9504 9.32211L30.2979 22.0813L25.3784 30.6092C23.4989 33.7121 21.3637 34.8426 18.0484 34.8426Z" fill="#00DC82" />
          </svg>
        </a>
        <h1 class="text-white text-4xl sm:text-5xl font-semibold text-center">
          Willkommen zu Nuxt bei Profihost!
        </h1>
      </div>
      <div class="grid grid-cols-2 lg:grid-cols-10 gap-6 max-w-[960px] px-4">
        <div class="col-span-2 lg:col-span-10 relative get-started-gradient-border">
          <div class="get-started-gradient-left absolute left-0 inset-y-0 w-[20%] bg-gradient-to-r to-transparent from-green-400 rounded-xl z-1 transition-opacity duration-300"></div>
          <div class="get-started-gradient-right absolute right-0 inset-y-0 w-[20%] bg-gradient-to-l to-transparent from-blue-400 rounded-xl z-1 transition-opacity duration-300"></div>
          <div class="w-full absolute inset-x-0 flex justify-center -top-[58px]">
            <img src="/icons/get-started.svg" class="block">
            <img src="/icons/get-started-light.svg" class="hidden">
          </div>
          <div class="flex flex-col rounded-xl items-center gap-y-4 pt-[58px] px-4 sm:px-28 pb-6 z-10">
            <h2 class="font-semibold text-2xl text-white">
              Erklärung
            </h2>
            <p class="mb-2 text-center">
                Diese Seite dient als Beispiel zur Visualisierung von Nuxt auf einem Profihost-Server. Die unteren Boxen dieser Seite sind verlinkt und führen zu den offiziellen Nuxt Seiten sowie zu Dokumentationen und Beispielen zum Setup bei Profihost!
            </p>
            </div>
        </div>
        <div class="lg:min-h-min sm:min-h-[220px] md:min-h-[180px] col-span-2 sm:col-span-1 lg:col-span-6 text-white rounded-xl modules-container relative items-center justify-center border border-transparent hover:border-transparent">
          <div class="gradient-border gradient-border-modules gradient-border-rect"></div>
          <div class="modules-gradient-right absolute right-0 inset-y-0 w-[20%] bg-gradient-to-l to-transparent from-yellow-400 rounded-xl z-1 transition-opacity duration-300"></div>
          <a href="/tutorial" target="_blank" class="py-6 px-5 rounded-xl flex items-center justify-center gap-x-4 border-none bg-gray-900 sm:min-h-[220px] md:min-h-[180px] lg:min-h-min">
            <img src="/icons/modules-color-light.svg" alt="modules icon" class="modules-image-color-light">
            <img src="/icons/modules-color.svg" alt="modules icon" class="modules-image-color-dark">
            <img src="/icons/modules-light.svg" alt="modules icon" class="modules-image-light">
            <img src="/icons/modules.svg" alt="modules icon" class="modules-image-dark">
            <div class="flex flex-col space-y text-white">
              <h3 class="font-semibold text-xl">
                Tutorial (Webversion)
              </h3>
              <p class="text-gray-300">
                Öffne die Dokumentation zur Installation auf Profihost Servern und folge den Anweisungen in der Webversion.
              </p>
            </div>
          </a>
        </div>
        <div class="row-span-2 col-span-2 order-last lg:order-none lg:col-span-4 text-white documentation-container rounded-xl relative items-center justify-center border border-transparent hover:border-transparent">
          <div class="gradient-border gradient-border-square gradient-border-documentation"></div>
          <a href="https://nuxt.com/docs" target="_blank" class="rounded-xl flex lg:flex-col items-center justify-center gap-y-4 bg-gray-900">
            <div class="py-6 lg:py-7 px-5 rounded-xl flex flex-col sm:flex-row lg:flex-col items-center justify-center gap-y-2 ">
                <div class="flex flex-col space-y text-white">
                <h3 class="font-semibold text-xl">
                  Dokumentation
                </h3>
                <p class="text-gray-300">
                  Wir empfehlen dringend einen Blick in die Nuxt-Dokumentation, um deine Kenntnisse zu vertiefen.
                </p>
              </div>
              <img src="/icons/documentation-color-light.svg" alt="documentation icon" class="documentation-image-color-light h-32 sm:h-34">
              <img src="/icons/documentation-color.svg" alt="documentation icon" class="documentation-image-color-dark h-32 sm:h-34">
              <img src="/icons/documentation-light.svg" alt="documentation icon" class="documentation-image-light h-32 sm:h-34">
              <img src="/icons/documentation.svg" alt="documentation icon" class="documentation-image-dark h-32 sm:h-34">
            </div>
          </a>
        </div>
        <div class="lg:min-h-min sm:min-h-[220px] md:min-h-[180px] col-span-2 sm:col-span-1 lg:col-span-6 text-white rounded-xl examples-container relative items-center justify-center border border-transparent hover:border-transparent">
          <div class="gradient-border gradient-border-examples gradient-border-rect"></div>
          <div class="examples-gradient-right absolute right-0 inset-y-0 w-[20%] bg-gradient-to-l to-transparent from-blue-400 rounded-xl z-1 transition-opacity duration-300"></div>
          <a href="https://github.com/haupt-pascal/profihost-nuxt" target="_blank" class="py-6 px-5 rounded-xl flex items-center justify-center gap-x-4 bg-gray-900 sm:min-h-[220px] md:min-h-[180px] lg:min-h-min">
            <img src="/icons/examples-color-light.svg" alt="examples icon" class="examples-image-color-light">
            <img src="/icons/examples-color.svg" alt="examples icon" class="examples-image-color-dark">
            <img src="/icons/examples-light.svg" alt="examples icon" class="examples-image-light">
            <img src="/icons/examples.svg" alt="examples icon" class="examples-image-dark">
            <div class="flex flex-col space-y text-white">
              <h3 class="font-semibold text-xl">
                Tutorial (Markdown @GitHub)
              </h3>
              <p class="text-gray-300">
                Öffne die Dokumentation zur Installation auf Profihost Servern und folge den Anweisungen in der Markdown Version.
              </p>
            </div>
          </a>
        </div>
      </div>
    </div>
    <footer class="relative border-t bg-black border-gray-900 w-full h-[70px] flex items-center">
      <div class="absolute inset-x-0 flex items-center justify-center -top-3">
        <a href="https://nuxt.com" target="_blank">
          <svg width="70" height="20" viewBox="0 0 70 20" fill="none" xmlns="http://www.w3.org/2000/svg">
            <ellipse cx="34.6528" cy="10.4209" rx="34.5" ry="9.5" fill="white" class="hidden" />
            <ellipse cx="34.6528" cy="10.4209" rx="34.5" ry="9.5" fill="black" class="block" />
            <path d="M36.0605 15.9209H42.6256C42.8341 15.9209 43.0389 15.8655 43.2195 15.7602C43.4001 15.6548 43.55 15.5033 43.6543 15.3209C43.7585 15.1384 43.8133 14.9315 43.8132 14.7208C43.8131 14.5102 43.7581 14.3033 43.6537 14.1209L39.2448 6.40667C39.1406 6.22427 38.9907 6.0728 38.8101 5.96748C38.6296 5.86217 38.4248 5.80672 38.2163 5.80672C38.0078 5.80672 37.803 5.86217 37.6225 5.96748C37.4419 6.0728 37.292 6.22427 37.1878 6.40667L36.0605 8.38048L33.8563 4.52076C33.752 4.33837 33.602 4.18692 33.4214 4.08163C33.2409 3.97633 33.036 3.9209 32.8275 3.9209C32.619 3.9209 32.4141 3.97633 32.2335 4.08163C32.053 4.18692 31.903 4.33837 31.7987 4.52076L26.3123 14.1209C26.2079 14.3033 26.1529 14.5102 26.1528 14.7208C26.1527 14.9315 26.2076 15.1384 26.3118 15.3209C26.416 15.5033 26.5659 15.6548 26.7465 15.7602C26.9271 15.8655 27.1319 15.9209 27.3405 15.9209H31.4615C33.0943 15.9209 34.2984 15.1964 35.127 13.7829L37.1385 10.2638L38.216 8.38048L41.4496 14.0376H37.1385L36.0605 15.9209ZM31.3943 14.0356L28.5184 14.035L32.8294 6.49263L34.9805 10.2638L33.5402 12.7844C32.99 13.7015 32.3649 14.0356 31.3943 14.0356Z" fill="#00DC82" />
          </svg>
        </a>
      </div>

      <div class="mx-auto sm:px-6 lg:px-8 px-4 w-full">
        <div class="flex flex-col items-center gap-3 sm:flex-row sm:justify-between">
          <div class="flex flex-col-reverse items-center gap-3 sm:flex-row">
            <span class="text-sm text-gray-300">© 2016-{{ new Date().getFullYear() }} Nuxt - MIT
                License</span>
          </div>

          <ul class="flex items-center justify-end gap-3">
            <li>
              <a
                href="https://github.com/haupt-pascal"
                target="_blank"
                class="focus-visible:ring-2  text-gray-300 hover:text-white"
              >
                <span class="sr-only">Nuxt GitHub Repository</span>
                <svg width="18" height="18" viewBox="0 0 18 18" fill="none" xmlns="http://www.w3.org/2000/svg">
                  <path d="M9.15269 0.792969C7.17392 0.793051 5.25974 1.49723 3.75266 2.77951C2.24558 4.06179 1.24394 5.83849 0.92697 7.7917C0.609997 9.74492 0.998373 11.7472 2.02261 13.4403C3.04684 15.1333 4.6401 16.4067 6.51729 17.0325C6.93396 17.1055 7.09021 16.8555 7.09021 16.6367C7.09021 16.4388 7.07978 15.7825 7.07978 15.0846C4.98603 15.47 4.44436 14.5742 4.27769 14.1055C4.09276 13.6496 3.79959 13.2456 3.42353 12.9284C3.13186 12.7721 2.71519 12.3867 3.4131 12.3763C3.67959 12.4052 3.93518 12.498 4.15822 12.6467C4.38125 12.7953 4.56516 12.9956 4.69436 13.2305C4.80833 13.4352 4.96159 13.6155 5.14535 13.7609C5.32911 13.9063 5.53975 14.014 5.76522 14.0779C5.99068 14.1418 6.22653 14.1605 6.45926 14.1331C6.69198 14.1056 6.917 14.0325 7.12143 13.918C7.1575 13.4943 7.34631 13.0982 7.65269 12.8034C5.79853 12.5951 3.86103 11.8763 3.86103 8.68883C3.84931 7.86062 4.15493 7.05931 4.71519 6.44924C4.46043 5.72943 4.49024 4.93948 4.79853 4.24091C4.79853 4.24091 5.49642 4.02215 7.09019 5.09508C8.45376 4.72005 9.89328 4.72005 11.2569 5.09508C12.8506 4.01174 13.5485 4.24091 13.5485 4.24091C13.8569 4.93947 13.8867 5.72943 13.6319 6.44924C14.1938 7.05826 14.4997 7.86027 14.486 8.68883C14.486 11.8867 12.5381 12.5951 10.6839 12.8034C10.8828 13.005 11.036 13.247 11.133 13.513C11.2301 13.779 11.2688 14.0628 11.2464 14.3451C11.2464 15.4597 11.236 16.3555 11.236 16.6367C11.236 16.8555 11.3923 17.1159 11.8089 17.0326C13.6828 16.4016 15.2715 15.1253 16.2914 13.4313C17.3112 11.7374 17.6959 9.73616 17.3768 7.78483C17.0576 5.83351 16.0553 4.05911 14.5489 2.77839C13.0425 1.49768 11.1299 0.793998 9.15269 0.792969Z" fill="currentColor" />
                </svg>
              </a>
            </li>
          </ul>
        </div>
      </div>
    </footer>
</div>
</template>