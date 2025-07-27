<template>
  <!-- <nav>
    <img src="@/assets/GreenTechLogo.png" alt="GreenTech Logo" id="greentechlogo"/>
  </nav> -->
  <div class="column">
    <h1>Contact Form</h1>
    <ContactForm
      msg="Have Us Reach Out"
      :FirstName="FirstName"
      :LastName="LastName"
      :Email="Email"
      :PhoneNumber="PhoneNumber"
      :CompanyName="CompanyName"
    />
  </div>
  <!-- <h1>{{ msg }}</h1>
  <input type="text" v-bind:id="'firstName'" v-model="FirstName" placeholder="First Name" />
  <input type="text" v-bind:id="'lastName'" v-model="LastName" placeholder="Last Name" />
  <input type="email" v-bind:id="'email'" v-model="Email" placeholder="Email" />
  <input type="tel" v-bind:id="'phoneNumber'" v-model="PhoneNumber" placeholder="Phone Number" />
  <input type="text" v-bind:id="'companyName'" v-model="CompanyName" placeholder="Company Name" /> -->
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "ContactPage",
  props: {
    msg: String,
    FirstName: String,
    LastName: String,
    Email: String,
    PhoneNumber: String,
    CompanyName: String,
  },
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
