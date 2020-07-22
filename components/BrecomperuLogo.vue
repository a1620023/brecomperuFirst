<template>
  <div>
    <v-row>
      <img
    class="BrecomperuLogo"
    alt="Brecomperu Logo"
    src="/bp/company-alas-esfera-icon.svg">
    </v-row>
    <v-row>
      <img
    alt="Brecomperu Logo"
    src="/bp/company-name.svg">
    </v-row>
  </div>
</template>

<style>
.BrecomperuLogo {
  height: 280px;
  width: 280px;
  transform: rotateY(360deg);
  animation: turn 3s ease-out infinite 1s;
}

@keyframes turn {
  100% {
    transform: rotateY(0deg);
  }
}
</style>
