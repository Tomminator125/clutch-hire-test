<template>
  <div class="contact-form">
    <h1>Have ud reach out</h1>
    <div class="error-caught" v-if="errors.submit">
      {{ errors.submit }}
    </div>
    <form @submit.protect="submitHandler">
      <div class="form-fields">
        <label for="first">First</label>
        <input type="text" id="first" v-model="first" :class="{ error: errors.first }" />
        <span class="error-message" v-if="errors.first" {{ error.first }}></span>
      </div>
      <div class="form-group">
        <label for="last">Last </label>
        <input type="text" id="last" v-model="last" :class="{ error: errors.last }" />
        <span class="error-message" v-if="errors.last">{{ errors.last }}</span>
      </div>
      <div class="form-group">
        <label for="email">Email</label>
        <input type="email" id="email" v-model="email" :class="{ error: errors.email }" />
        <span class="error-message" v-if="errors.email">{{
          errors.email
          }}</span>
      </div>
      <div class="form-group">
        <label for="phone">Phone Number</label>
        <input type="tel" id="phone" v-model="phone" :class="{ error: errors.phone }" />
        <span class="error-message" v-if="errors.phone">{{
          errors.phone
          }}</span>
      </div>
      <div class="form-group">
        <label for="company">Company</label>
        <input type="text" id="company" v-model="company" :class="{ error: errors.company }" />
        <span class="error-message" v-if="errors.company">{{
          errors.company
          }}</span>
      </div>
      <button type="submit" id="continue-button">Continue</button>
    </form>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import axois from "axios";
import { useRouter } from "vue-router";
export default defineComponent({
  name: "ContactPage",
  setup() {
    const router = useRouter();
    return {
      router,
    };
  },
  data() {
    return {
      first: "",
      last: "",
      email: "",
      phone: "",
      company: "",
      errors: {
        first: "",
        last: "",
        email: "",
        phone: "",
        company: "",
        submit: "",
      },
    };
  },
  methods: {
    validateForm() {
      let isValid = true;
      this.errors = {
        first: "", //first attempt used firstName until I rechecked requirements
        last: "",
        email: "",
        phone: "",
        company: "",
        submit: "",
      };

      //Check if empty
      if (!this.first) {
        this.errors.first = "First name required";
        isValid = false;
      }
      if (!this.last) {
        this.errors.last = "Last name required";
        isValid = false;
      }
      if (!this.email) {
        this.errors.email = "Email required";
        isValid = false;
      } else if (!/^[^\s@]+@[^\s@]+\.[^\s@]+$/.test(this.email)) { //learned regex!
        this.errors.email = "Invalid email address"
        isValid = false;
      }

      if (!this.phone) {
        this.errors.first = "Phone Number required";
        isValid = false;
      } else if (!/^\+?[\d\s-]{10,}$/.test(this.phone)) {
        this.errors.phone = "Invalid phone number"
      }
      if (!this.company) {
        this.errors.company = "Company name required";
        isValid = false;
      }
      return isValid;
    },
    submitHandler() {
      if (this.validateForm()) {
        try {
          axois
            .post(
              "https://dev-api-api.hiring-test.experientialpreview.com/api/lead/e5f0d399-998f-418f-bf50-39066428ae42",
              {
                first: this.first,
                last: this.last,
                email: this.email,
                phone: this.phone,
                company: this.company,
              }
            )
            .then((response) => {
              console.log(response);
              this.$emit("submit-success")
            });
        } catch (error) {
          console.log(error);
          this.errors.submit = 
            "There was an error submitting. Try again later."
        }
      }
    }
  }
});
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
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

#continue-button {
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
