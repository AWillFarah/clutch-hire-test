<template>
  <div class="hello">
    <img src="../assets/greentech.png" alt="Logo" class="logo" />
    <div class="whitespace"></div>
    <div v-if="!thankYou">
      <h1>Have us reach out</h1>

      <form @submit.prevent="handleSubmit">
        <label for="first">First Name</label>
        <br />
        <input
          type="text"
          id="first"
          name="first"
          required
          v-model="form.first"
        /><br />
        <label for="last">Last Name</label>
        <br />
        <input
          type="text"
          id="last"
          name="last"
          required
          v-model="form.last"
        /><br />
        <label for="email">Email</label>
        <br />
        <input
          type="email"
          id="email"
          name="email"
          required
          v-model="form.email"
        /><br />
        <label for="phone">Phone Number</label>
        <br />
        <input
          type="tel"
          id="phone"
          name="phone"
          required
          v-model="form.phone"
          pattern="\d{10}"
        /><br />
        <label for="company">Company</label>
        <br />
        <input
          type="text"
          id="company"
          name="company"
          required
          v-model="form.company"
        /><br />
        <input type="submit" value="Continue" /><br />
      </form>
    </div>
  </div>
  <div class="thank-you" v-if="thankYou">
    Thank you <br /><br />
    We will contact you shortly
  </div>
</template>

<script>
import { AsYouTypeFormatter } from "libphonenumber-js";

export default {
  data() {
    return {
      form: {
        first: "",
        last: "",
        email: "",
        phone: "",
        company: "",
      },
      thankYou: false,
      // Going to write comments galore for this here since im the least certain about this
      apiUrl:
        "https://dev-api-api.hiring-test.experientialpreview.com/api/lead/3e430654-949b-4c46-bbfe-5afb7f6d37ac",
    };
  },
  methods: {
    async handleSubmit(event) {
      // Well this is pretty straightforward, it's going to "try" to submit the data here
      try {
        console.log("Submitting form data to API:", this.form);
        // Here we are trying to post data to the URL
        const response = await fetch(this.apiUrl, {
          method: "POST",
          headers: {
            "Content-Type": "application/json",
          },
          // The body here is the stuff we actually send to the API
          body: JSON.stringify(this.form),
        });
        if (response.ok) {
          console.log("Form data submitted successfully");
        } else {
          console.error("Failed to submit form data:", response.statusText);
        }
      } catch (error) {
        console.error("Error submitting form data:", error);
      }
      this.thankYou = true;
      // Reset the form
      this.form.first = "";
      this.form.last = "";
      this.form.email = "";
      this.form.phone = "";
      this.form.company = "";
      setTimeout(() => {
        this.thankYou = false;
      }, 5000);
    },
  },
};
</script>

<style scoped lang="scss">
.hello {
  margin: 30px 17.5px;
}
img {
  width: 122.82685852050781px;
  height: 40px;
  top: 30px;
  left: 35px;
  opacity: 1;
}

.whitespace {
  height: 138px;
}

h1 {
  font-family: "Roboto", sans-serif;
  font-size: 25px;
  color: #555552;
  width: 310px;
  height: 29px;
  top: 208px;
  left: 36px;
  angle: 0deg;
  opacity: 1;
}

label {
  font-family: "AbeeZee", sans-serif;
  font-weight: 400;
  height: 17.27px;

  position: relative;
  bottom: -10px;
  left: 12px;

  font-style: Regular;
  font-size: 12px;
  text-align: center;
  leading-trim: NONE;
  line-height: 100%;
  letter-spacing: 0%;
  text-indent: 0%;
  padding: 1.26px 6.32px;
  background-color: white;
  color: #006315;
}
input {
  width: 310px;
  height: 40.31999969482422px;

  border-radius: 3.6px;
  border-width: 0.72px;
  border-color: #555552;

  color: #555552;
  font-family: "AbeeZee", sans-serif;

  padding-left: 20.1px;
  font-size: 15px;
  font-weight: 400;
}
input[type="submit"] {
  background-color: #0b476c;
  color: white;
  font-size: 13.45px;
  width: 131px;
  height: 34.83px;
  border-radius: 4px;
  border: none;

  position: relative;
  top: 92px;
  left: 180px;
  border-radius: 4px;
  padding-top: 10.22px;
  padding-right: 37.5px;
  padding-bottom: 8.61px;
  padding-left: 37.5px;
  gap: 5.38px;
}
.thank-you {
  width: 227px;
  height: 116px;
  left: 65.5px;
  top: 183px;
  horizontal-align: center;
  font-family: Roboto;
  font-weight: 400;
  font-style: Regular;
  font-size: 25px;
  line-height: 100%;
  text-align: center;
  color: #555552;
  position: relative;
}
</style>
