<template>
  <div class="login-container">
    <div class="login-body">
      <div class="login-form">
        <div class="mgm-logo">
          <img src="@/assets/mgm.png" class="logo-text-mgm" aria-label="MGM">
          <span class="mgm-global">
            <div>Global</div>
            <div>Distribution</div>
          </span>
        </div>
        <div class="signin">Sign in</div>
        <form @submit.prevent="handleSubmit" aria-label="Login Form">
          <div class="form-group">
            <label for="email" class="label-left">Email</label>
            <input type="email" id="email" name="email" v-model="email" placeholder="Enter your email address"
            aria-required="true" aria-describedby="email-error" required />
          </div>
          <div class="form-group">
            <label for="password" class="label-left">Password</label>
            <input type="password" id="password" name="password" v-model="password" placeholder="Enter your password"
            aria-required="true" aria-describedby="password-error" required />
          </div>
          <div class="forgot-password" aria-label="Forgot Password">
            <a>Forgot Password?</a>
          </div>
          <div class="checkbox-label">
            <input type="checkbox" id="remember-me" name="remember-me" v-model="rememberMe" aria-label="Keep me signed in for 30 days" />
            <div>Keep me signed in for 30 days</div>
          </div>
          <button type="submit" class="button">SIGN IN</button>
          <div class="terms-of-service">
            <span class>
              Read our Terms of Service
            </span>
            <img src="@/assets/policy logo.png" class="service-policy-logo" alt="(Terms of Service)">
          </div>
        </form>
      </div>
      <div class="prefotter"></div>
      <div class="fotter">
        <p>OTHER WAYS TO WATCH</p>
        <div class="fotter-images">
        <img src="@/assets/apple-tv.png" alt="Apple TV" aria-label="Apple TV" />
        <img src="@/assets/ios.png" alt="IOS" aria-label="iOS">
        <img src="@/assets/Roku.png" alt="Roku" aria-label="Roku">
        <img src="@/assets/amazon fire.png" alt="Amazon Fire" aria-label="Amazon Fire">
        </div>
        <p>Search for AppleTV+ FYC on your App Store</p>
      </div>
    </div>
    <div class="overlay" v-if="showOverlay" aria-hidden="true" aria-live="assertive" aria-busy="true">
      <div class="overlay-content">
        <img
          src="https://static.vecteezy.com/system/resources/previews/033/294/018/original/fill-green-tick-mark-approved-check-mark-icon-symbols-symbol-for-website-computer-and-mobile-isolated-green-tick-verified-badge-icon-social-media-official-account-tick-symbol-vector.jpg"
          alt="Success" class="tick-icon">
        <p>Login successful!</p>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      email: "",
      password: "",
      rememberMe: false,
      showOverlay: false,
    };
  },
  methods: {
    handleSubmit() {
      if (this.password.length < 8) {
        alert("Password must be at least 8 characters long");
        return;
      }
      // Simulate login process
      this.showOverlay = true;
      // Simulate delay for 2 seconds then hide overlay
      setTimeout(() => {
        this.showOverlay = false;
      }, 1000);
    },
  },
};
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Noto+Sans:ital,wght@0,100..900;1,100..900&display=swap');

.login-container {
  margin: 0;
  padding: 0;
  height: 100vh;
  width: 100vw;
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: center;
  background-image: url("https://s3-alpha-sig.figma.com/img/0c37/0203/0959257e0ec7de02b8038c0959e0e9bd?Expires=1715558400&Key-Pair-Id=APKAQ4GOSFWCVNEHN3O4&Signature=J8IplukyrwYUkq66oTdXBjn1pIhL2I1PmhOpiS8827AaL9CWDLm4k0BVsWF1-jasFiaw5-NPJiUlCCr3iB7BZxEoukY5h7vxQCHihvwLqGq3jCzVRSXDb8zMXR~yqPE6REFcv01QlcsPMwzHo18xNbqilJIXvtMpo2dGF06W6PL6eBJ1HP8aMuNgYn82kjIVszHyG8n-zqehRtd~kmzcJ32HrgK3wKiRFtyrlHNcVvazDLb0-bCbeV26WENVQRIApx5OvpRSAac0M60kqotAFTg9sA8b-h7PVrDJycwDYuO9pIywJSlGVcoKsb8Q3f-V8SgKUCbmWqgatZFkHdcT2g__");
  background-size: cover;
}

.login-container::before {
  /* Add pseudo-element for overlay */
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background-color: rgba(0, 0, 0, 0.75);
  /* Semi-transparent black overlay */
  z-index: 0;
  /* Place under other content */
}

.login-body {
  margin-top: -2%;
  height: 88.40%;
  width:428px
}

.mgm-logo {
  display: flex;
  flex-direction: row;
  justify-content: center;
  font-family: "Noto Sans", serif;
  height: 5.81%;
  /* margin-bottom: 32.4px; */
}

.mgm-global {
  margin: 0;
  padding: 0;
  display: flex;
  flex-direction: column;
  height: 100%;
}

.mgm-global div {
  margin: 0;
  padding: 0;
  text-align: left;
  
  height: 50%;
}

.logo-text-mgm {
  height: 140%;
  line-height: 1;
  margin-right: 4.5px;
}

.signin {
  text-align: left;
  margin-bottom: 30.4px;
  margin-top: 11.5%;
  font-size: 100%;
  height: 2.5%;
}

.login-form {
  width: 74.8%;
  height: 78.86%;
  padding: 12.65%;
  padding-top: 45px;
  border-radius: 5px 5px 0 0;
  padding-bottom: 0;
  background-color: rgba(0, 0, 0, 0.5);
  backdrop-filter: blur(10px);
  color: white;
  /* box-shadow: 0 0 20px rgba(0, 0, 0, 0.5); */
  text-align: center;
  font-family: "Noto Sans", sans-serif;
}

.login-form form{
  height: 69.42%;
}


.form-group {
  height: 15.49%;
  margin-bottom: 25.2px;
}


.form-group input {
  width: 100%;
  height: 67.59%;
  padding: 9px;
  color: rgb(213, 213, 213);
  border: 1px solid #444444;
  border-radius: 2.7px;
  box-sizing: border-box;
  background-color: rgb(36, 36, 36);
  /* Set input background color to black */
  align-self: flex-start;
}

.label-left {
  color: rgb(0, 133, 239);
  font-weight: 540;
  font-size: 74%;
  height: 17.6%;
  text-align: left;
  display: block;
  margin-bottom: 4.11%;
}

.forgot-password {
  text-align: right;
  margin-top: -10px;
  font-size: 65%;
  color: rgb(188, 188, 188);
  margin-bottom: 20px;
}

.forgot-password:hover {
  cursor: pointer;
}

.checkbox-label input[type="checkbox"] {
  margin-right: 9px;
  /* Adjust spacing between checkbox and text */
  background-color: transparent;
  /* Set checkbox background to transparent */
  width: 16.5px;
  /* Set checkbox width */
  height: 16.5px;
  /* Set checkbox height */
  -webkit-appearance: none;
  /* Remove default styling */
  -moz-appearance: none;
  appearance: none;
  border: 1px solid rgb(188, 188, 188);
  /* Add border to checkbox for better visibility */
  border-radius: 2.7px;
  /* Add border radius for a rounded look */
}


.checkbox-label input[type="checkbox"]:checked::before {
  content: "\2713";
  /* Unicode character for checkmark */
  font-size: 16.2px;
  /* Adjust size of checkmark */
  line-height: 1;
  /* Ensure checkmark is vertically centered */
  color: rgb(188,188,188);
  /* Color of the checkmark */
  display: inline-block;
  width: 18px;
  /* Set width of the checkmark */
  height: 18px;
  /* Set height of the checkmark */
  text-align: center;
  /* Center the checkmark horizontally */
}

.checkbox-label div{
  font-size: 65%;
  color: rgb(188, 188, 188)
}

.checkbox-label {
  display: flex;
  align-items: center;
  color: white;
}

.form-group input::placeholder {
  color: rgb(188,188,188);
  font-size: 84%;
  font-weight: 450
}

.form-group a {
  color: #333;
  text-decoration: none;
}

.form-group a:hover {
  text-decoration: underline;
}

.button {
  width: 100%;
  font-family: "Noto Sans", sans-serif;
  font-size: 1.08rem;
  background-color: rgb(0, 87, 255);
  color: #fff;
  padding: 9px 18px;
  border: none;
  border-radius: 2.7px;
  cursor: pointer;
  word-spacing: 1.8px;
  letter-spacing: 1.8px;
  margin-top: 36px;
}

.overlay {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-color: rgba(0, 0, 0, 0.7);
  display: flex;
  justify-content: center;
  align-items: center;
  z-index: 999;
}

.overlay-content {
  background-color: #fff;
  padding: 20px;
  border-radius: 5px;
  text-align: center;
}

.tick-icon {
  width: 50px;
  margin-bottom: 20px;
}

.terms-of-service {
  display: flex;
  flex-direction: row;
  align-items: flex-start;
  margin-top: 40px;
}

.terms-of-service span {
  color: rgb(179, 170, 170);
  font-size: 68%;
  margin-right: 0.5%
}

.service-policy-logo {
  height: 14.5px;
}

.prefotter {
  height: 5.655%;
  background-color: #ccdbe2;
  z-index: 2;
}

.fotter {
  height: 15.475%;
  background-color: rgb(118, 129, 147);
  z-index: 6;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: space-evenly;
}
.fotter p{
  margin: 0;
  font-size: 60%;
  color: rgb(213, 213, 213);
  z-index: 6;
}
.fotter-images{
  display: flex;
  flex-direction: row;
  align-items: center;
  justify-content: space-around;
  width: 65%;
  text-align: center;
}
.fotter img{
  height: 24px;
  z-index: 6;
}

@media screen and (max-width: 480px){
.login-body{
  margin-top: -8%;
}
.login-body {
    width: 90%; /* Adjust width for smaller screens */
}

}

</style>