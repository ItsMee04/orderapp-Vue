<template lang="">
  <div class="main-wrapper">
    <div class="account-content">
      <div class="login-wrapper login-new">
        <div class="container">
          <div class="login-content user-login">
            <div class="login-logo">
              <img src="/src/assets/img/logo.png" alt="img" />
              <a href="/login" class="login-logo logo-white">
                <img src="/src/assets/img/logo-white.png" alt />
              </a>
            </div>
            <form @submit.prevent>
              <div class="login-userset">
                <div class="login-userheading">
                  <h3>Sign In</h3>
                  <h4>
                    Access the Dreamspos panel using your email and passcode.
                  </h4>
                </div>
                <div class="form-login">
                  <label class="form-label">Email Address</label>
                  <div class="form-addons">
                    <input type="email" v-model="email" class="form-control" />
                    <img src="/src/assets/img/icons/mail.svg" alt="img" />
                  </div>
                </div>
                <div class="form-login">
                  <label>Password</label>
                  <div class="pass-group">
                    <input
                      type="password"
                      v-model="password"
                      class="pass-input"
                    />
                    <span class="fas toggle-password fa-eye-slash"></span>
                  </div>
                </div>
                <div class="form-login authentication-check">
                  <div class="row">
                    <div class="col-6">
                      <div class="custom-control custom-checkbox">
                        <label class="checkboxs ps-4 mb-0 pb-0 line-height-1">
                          <input type="checkbox" />
                          <span class="checkmarks"></span>Remember me
                        </label>
                      </div>
                    </div>
                    <div class="col-6 text-end">
                      <a class="forgot-link" href="forgot-password-3.html"
                        >Forgot Password?</a
                      >
                    </div>
                  </div>
                </div>
                <div class="form-login">
                  <button class="btn btn-login" @click="login()">
                    Sign In
                  </button>
                </div>
                <div class="signinform">
                  <h4>
                    New on our platform?<a
                      href="register-3.html"
                      class="hover-a"
                    >
                      Create an account</a
                    >
                  </h4>
                </div>
              </div>
            </form>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import router from "@/router";
import axios from "axios";

export default {
  data() {
    return {
      email: "",
      password: "",
    };
  },

  methods: {
    login() {
      axios
        .post("http://127.0.0.1:8000/api/auth/login", {
          email: this.email,
          password: this.password,
        })
        .then(function (response) {
          localStorage.setItem("email", response.data.data.email);
          localStorage.setItem("name", response.data.data.name);
          localStorage.setItem("role_id", response.data.data.role_id);
          localStorage.setItem("token", response.data.data.token);

          router.push({ name: "home" });
        })
        .catch(function (error) {
          console.log(error);
        });
    },
  },

  mounted() {
    this.email = localStorage.getItem("email");
    if (this.email || this.email != null) {
      router.push({ name: "home" });
    }
  },
};
</script>
