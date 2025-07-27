<template>
  <div class="hello">
    <img src="../assets/greentech.png" alt="Logo" class="logo" />
    <div class="whitespace"></div>
    <h1>Have us reach out</h1>

    <form>
      <label for="first">First Name</label>
      <br />
      <input type="text" id="first" name="first" /><br />
      <label for="last">Last Name</label>
      <br />
      <input type="text" id="last" name="last" /><br />
      <label for="email">Email</label>
      <br />
      <input type="email" id="email" name="email" /><br />
      <label for="phone">Phone Number</label>
      <br />
      <input type="text" id="phone" name="phone" /><br />
      <label for="company">Company</label>
      <br />
      <input type="text" id="company" name="company" /><br />
      <input type="submit" value="Continue" /><br />
    </form>
  </div>
</template>

<script lang="ts"></script>

<style scoped lang="scss">
.hello {
  margin: 30px 35px;
}
img {
  width: 122.82685852050781px;
  height: 40px;
  top: 30px;
  left: 35px;
  opacity: 1;
}

.whitespace {
  height: 178px;
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
</style>
