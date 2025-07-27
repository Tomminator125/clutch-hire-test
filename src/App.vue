<script setup>
  import { ref } from 'vue';

  const FirstName = ref("John");
  const LastName = ref("Doe");
  const Email = ref("johndoe@example.com");
  const PhoneNumber = ref("123-456-7890");
  const CompanyName = ref("Example Corp");
</script>
<template>
    <nav>
    <img src="@/assets/GreenTechLogo.png" alt="GreenTech Logo" id="greentechlogo"/>
  </nav>
  <router-view />
</template>

<style lang="scss">
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

label {
  font-family: ABeeZee;
  font-weight: 400;
  font-style: Regular;
  font-size: 12px;
  line-height: 100%;
  letter-spacing: 0%;
  background: #006315;
  //Values from Figma
}

input {
  width: 310;
  height: 40.31999969482422;
  top: 334.23px;
  left: 35.76px;
  opacity: 1;
  border-radius: 3.6px;
  border-width: 0.72px;
  border: 0.72px solid #555552;
  //Values from Figma
}

#continuebutton {
  width: 131;
  height: 34.82982635498047;
  top: 640px;
  left: 215px;
  opacity: 1;
  padding-top: 10.22px;
  padding-right: 37.5px;
  padding-bottom: 8.61px;
  padding-left: 37.5px;
  gap: 5.38px;
  border-radius: 4px;
  background: #0B476C;
  color: #FFFFFF;
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
