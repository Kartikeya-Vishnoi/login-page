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
            aria-required="true" aria-describedby="password-error" class="closed-eye" minlength="8" 
            title="Password must be at least 8 characters long" required />
          </div>
          <div class="forgot-password" aria-label="Forgot Password">
            <a @click="handleForgotPasswordClick">Forgot Password?</a>
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
      <div class="prefooter"></div>
      <div class="footer">
        <p>OTHER WAYS TO WATCH</p>
        <div class="footer-images">
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
      // if (!this.email) {
      //   alert("Email field cannot be empty");
      //   return;
      // }
      // if (this.password.length < 8) {
      //   alert("Password must be at least 8 characters long");
      //   return;
      // }
      // Simulate login process
      this.showOverlay = true;
      // Simulate delay for 2 seconds then hide overlay
      setTimeout(() => {
        this.showOverlay = false;
        this.email = ""; // Clear email input
        this.password = ""; // Clear password input
      }, 1500);
    },
    handleForgotPasswordClick() {
      alert("Forgot Password clicked!");
    }
  },
};
</script>

<style scoped>
@import url("C:\Users\vishn\Desktop\Indee Project\indee_login_page\src\App.css");
</style>