<template>
  <v-container>
    <h1>Login</h1>
    <user-auth-form buttonText="Login" :submitForm="login"> </user-auth-form>
  </v-container>
</template>

<script>
import UserAuthForm from "@/components/UserAuthForm";

export default {
  components: {
    UserAuthForm,
  },
  methods: {
    login(credentials) {
      this.$store
        .dispatch("login", credentials)
        .then((res) => {
          this.$router.push("/");
        })
        .catch((e) => {
          console.log(e);
        });
    },
  },
};
</script>

<style lang="scss" scoped>
</style>