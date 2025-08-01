<template>
  <nav>
    <img src="@/assets/GreenTechLogo.png" alt="GreenTech Logo" id="greentechlogo" />
  </nav>
  <router-view />
</template>

<style lang="scss">
@import url("https://fonts.googleapis.com/css2?family=Roboto:wght@400;500;700&display=swap");
@import url("https://fonts.googleapis.com/css2?family=ABeeZee&display=swap");

html,
body,
#app {
  min-height: 100dvh;
  background-color: #F4F2EE;
}

#greentechlogo {
  width: 122.82685852050781;
  height: 40;
  top: 30px;
  left: 35px;
  opacity: 1;
  position: absolute;
  //Values from Figma
}

h1 {
  font-family: Roboto;
  font-weight: 400;
  font-style: Regular;
  font-size: 25px;
  line-height: 100%;
  letter-spacing: 0%;
  background: #555552;
  //Values from Figma
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.25s;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
