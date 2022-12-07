<template>
  <div class="try_again">
    <div class="text">      
      <router-link v-if="!isLoggedIn" to="/login"><button>Login</button></router-link>
      <router-link v-if="!isLoggedIn"  to="/register"><button>Register</button></router-link>
      <div v-if="isLoggedIn">
        <h1>Welcome!</h1>
        <Me/>
      </div>
      <div v-else>
        <h3>Invalid password/login or user does not exist.</h3>
        <h4>Try again or register ;)</h4>
      </div>
      <router-view></router-view>
    </div>
  </div>
</template>

<script>
import {mapGetters} from "vuex";
import Me from "@/components/Me";

export default {
  name: "Welcome",
  components: {Me},
  computed: {
    ...mapGetters(["isLoggedIn"])
  }
}
</script>
<style scoped>
  .try_again{
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    background-color: rgb(205, 93, 227);
  }

  .text{
    margin-left: auto;
    margin-right: auto;
    margin-top: auto;
    margin-bottom: auto;
    padding-top: 10px;
    padding-bottom: 10px;
    width: 500px;
    border: 1px solid black;
    background-color: rgb(210, 117, 228);
  }
</style>