<template>
    <svg id="about-icon" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" viewBox="0 0 347 248">
        <g id="person">
            <path
                class="cls-1"
                d="m289.97,89.42h-3.57v1.41c0,31.23,0,62.46,0,93.69,0,9.16.02,18.33-.03,27.49-.03,6.49-5.84,10.86-11.98,9.09-3.94-1.14-6.57-4.75-6.58-9.14-.02-9.37,0-18.75,0-28.12,0-13.83,0-27.66,0-41.49,0-.42,0-.84,0-1.36h-3.8c0,.48,0,.96,0,1.45,0,23.2,0,46.41-.02,69.61,0,6.47-5.81,10.81-11.99,9.03-3.34-.96-6.08-4.18-6.41-7.68-.14-1.54-.11-3.11-.11-4.66-.03-38-.05-76-.07-113.99,0-1.72,0-3.44,0-5.27h-3.51c0,.52,0,1.05,0,1.57,0,14,0,27.99,0,41.99,0,3.56-1.89,6.23-4.94,7.09-4.53,1.27-8.76-1.91-8.77-6.69-.03-9.79-.01-19.59-.01-29.38,0-6.35-.01-12.69,0-19.04.02-11.81,8.82-20.68,20.62-20.72,11.3-.04,22.61-.04,33.91,0,8.87.03,15.34,4.03,19.24,12.03,1.28,2.64,1.78,5.51,1.78,8.44,0,16.14,0,32.28-.02,48.42,0,3.4-1.82,5.99-4.7,6.88-2.97.91-6.17-.03-7.75-2.66-.76-1.26-1.21-2.91-1.22-4.38-.09-14-.05-27.99-.05-41.99,0-.5,0-1,0-1.62Z"
            />
            <path class="cls-1" d="m265.81,60.24c-8.7-.05-15.73-7.17-15.69-15.9.04-8.67,7.19-15.73,15.91-15.69,8.68.04,15.72,7.19,15.67,15.91-.05,8.73-7.14,15.73-15.89,15.68Z" />
        </g>
        <circle class="cls-2 orange-dot" cx="309.5" cy="187.5" r="11.5" />
        <circle class="cls-4 teal-dot" cx="225.5" cy="109.5" r="11.5" />
        <circle class="cls-5 purple-dot" cx="303.5" cy="61.5" r="11.5" />
        <g id="word-bubbles">
            <g id="shadow-top">
                <image
                    width="250"
                    height="121"
                    transform="translate(-13 -1)"
                    xlink:href="data:image/png;base64,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"
                />
            </g>
            <g id="shadow-mid">
                <image
                    width="244"
                    height="122"
                    transform="translate(4.33 63.87)"
                    xlink:href="data:image/png;base64,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"
                />
            </g>
            <g id="bubble-top">
                <path class="cls-3" d="m201,69l-33.3-20.19c-1.59-9.53-9.85-16.81-19.83-16.81H43.13c-11.12,0-20.13,9.01-20.13,20.13v8.74c0,11.12,9.01,20.13,20.13,20.13h104.74c9.77,0,17.91-6.97,19.74-16.2l33.39,4.2Z" />
                <g id="top-bubble">
                    <rect class="cls-5" x="64.23" y="51.8" width="77.46" height="8.61" />
                    <rect class="cls-5" x="44.94" y="52.42" width="8.84" height="8.52" />
                </g>
            </g>
            <g id="bibble-middle">
                <path class="cls-3" d="m211.61,118.74l-25.61-1.61c0-11.12-9.01-20.13-20.13-20.13H61.13c-11.12,0-20.13,9.01-20.13,20.13v8.74c0,11.12,9.01,20.13,20.13,20.13h104.74c9.83,0,18-7.05,19.76-16.36l25.97-10.9Z" />
                <g id="med-bubble">
                    <rect class="cls-4" x="82.23" y="116.97" width="77.46" height="8.61" />
                    <rect class="cls-4" x="62.94" y="117.58" width="8.84" height="8.52" />
                </g>
            </g>
            <g id="shadow-bottom">
                <image
                    width="261"
                    height="121"
                    transform="translate(-13 131)"
                    xlink:href="data:image/png;base64,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"
                />
            </g>
            <g id="bubble-bottom">
                <path class="cls-3" d="m211.61,164l-45.32,12s0,0,0,0c-3.12-7.07-10.18-12-18.41-12H43.13c-11.12,0-20.13,9.01-20.13,20.13v8.74c0,11.12,9.01,20.13,20.13,20.13h104.74c9.42,0,17.31-6.48,19.5-15.22l44.23-33.78Z" />
                <g id="bot-bubble">
                    <rect class="cls-2" x="63.84" y="184.66" width="77.46" height="8.61" />
                    <rect class="cls-2" x="44.55" y="185.28" width="8.84" height="8.52" />
                </g>
            </g>
        </g>
    </svg>
</template>

<script>
export default {
    name: 'AboutIcon',
}
</script>

<style lang="scss" scoped>
.cls-1{fill:none;stroke:#fff;stroke-miterlimit:10;stroke-width:6px;}.cls-2{fill:#f29e4c;}.cls-3{fill:#83e377;}.cls-4{fill:#0db39e;}.cls-5{fill:#54478c;}

@keyframes wander1 {
  34% {
    transform: translate(-2px, 0);
  }
  37% {
    transform: translate(12px, -8px);
  }
  100% {
    transform: translate(10px, 20px);
  }
}

@keyframes wander2 {
  34% {
    transform: translate(-20px, 10px);
  }
  37% {
    transform: translate(12px, -28px);
  }
  100% {
    transform: translate(10px, 20px);
  }
}

#about-icon {
    &:hover {
        .orange-dot {
            animation: wander1 3s ease infinite;
        }

        .teal-dot {
            animation: wander2 3s ease infinite;
        }

        .purple-dot {
            animation: wander1 3s ease reverse infinite;
        }
    }
}
</style>