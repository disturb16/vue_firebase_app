<template>
  <div class="container" style="text-align:left">
    <form class="col-lg-6 offset-md-3">
      <div class="form-group">
        <label for="email">Email address</label>
        <input
          type="email"
          class="form-control"
          id="email"
          v-model="email"
          aria-describedby="emailHelp"
        />
        <small id="emailHelp" class="form-text text-danger">{{
          emailError
        }}</small>
      </div>
      <div class="form-group">
        <label for="password">Password</label>
        <input
          type="password"
          class="form-control"
          id="password"
          v-model="password"
        />
        <small id="passwordHelp" class="form-text text-danger">{{
          passError
        }}</small>
      </div>
      <button class="btn btn-primary" @click.prevent="validateUser">
        Submit
      </button>
    </form>
  </div>
</template>

<script>
export default {
  name: "LoginUser",
  data() {
    return {
      email: "",
      password: "",
      emailError: "",
      passError: "",
    };
  },

  methods: {
    validateUser() {
      if (this.email.length == 0) {
        this.emailError = "El correo no puede estar vacio";
        return;
      } else if (this.password.length == 0 || this.password.length < 6) {
        this.passError = "La contraseña debe tener al menos 6 caracteres";
        return;
      }

      const payload = {
        id: 2,
        email: this.email,
        name: "Pedro",
      };

      this.$store.commit("setUser", payload);

      this.$router.push({ name: "Home" });
    },
  },
};
</script>
