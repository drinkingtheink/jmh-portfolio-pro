<template>
    <svg class="JH-monogram" data-name="Layer 1" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 285.06 318.32">
        <polygon
            class="mono-cls-1"
            points="257.18 73.95 285.06 63.13 218.06 63.13 218.06 89.13 218.08 89.12 218.08 132.85 203.06 132.85 203.06 157.5 218.08 157.5 218.08 209.13 218.06 209.13 218.06 235.13 218.08 235.13 257.18 235.13 285.06 235.13 257.18 224.31 257.18 73.95"
        />
        <path
            class="mono-cls-1"
            d="M154,6.87H25v67L37.89,40.65H156.48v98.77H131.1V70.36H131V70H64L92,80.86V231.14L64,242h67v-.3h.1V164.07h25.38v52.16c0,51.39-20,73.75-64.24,73.75-24.26,0-49-13.32-67.09-40.92L-.06,273.33C21.82,309,58.46,325.19,93.2,325.19c77.55,0,103.72-47.58,103.72-105.63V6.87Z"
            transform="translate(0.06 -6.87)"
        />
    </svg>

</template>

<script>
export default {
  name: 'JHMonogram',
}
</script>

<style lang="scss" scoped>
$col3: #0db39e;
$col4: #83e377;
$col5:#f29e4c;

@keyframes colorGrad {
  0% {
    fill: $col4;
  }
  20% {
    fill: $col4;
  }
  30% {
    fill: lightsalmon;
  }
  40% {
    fill: $col3;
  }
  60% {
    fill: $col4;
  }
  80% {
    fill: white;
  }
}

.mono-cls-1{fill: white;} 

.JH-monogram * {
    transition: all .3s;
    animation: colorGrad 20s alternate infinite;
}

.JH-monogram:hover {
    .mono-cls-1 {
        fill: white !important;
    }
}
</style>