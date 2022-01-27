<template>
  <div id="app">
    <b-container>
      <b-row class="pb-5">
        <b-col>
          <b-button variant="info" v-on:click="imprimir(users)"
            >Imprimir Usuarios en Consola</b-button
          >
        </b-col>
      </b-row>
      <b-row>
        <b-col lg="4" md="6" sm="12" v-for="user in users" :key="user.id">
          <User v-bind:userData="user" />
        </b-col>
      </b-row>
      <b-row class="pb-5">
        <b-col>
          <b-button variant="info" v-on:click="imprimir(users)"
            >Imprimir Usuarios en Consola</b-button
          >
        </b-col>
      </b-row>
    </b-container>
  </div>
</template>

<script>
import User from "./components/User.vue";
import axios from "axios";

const baseUrl = "https://reqres.in/api/users?page=2";

export default {
  name: "App",
  components: {
    User,
  },
  data() {
    return {
      users: [],
    };
  },
  mounted() {
    axios.get(baseUrl).then(({ data }) => {
      this.users = data.data;
    });
  },
  methods: {
    imprimir(users) {
        console.table(JSON.parse(JSON.stringify(users)));
    },
  },
};
</script>

<style lang="scss">
@import "~@/assets/scss/vendors/bootstrap-vue/index";

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
::-moz-selection {
  /* Code for Firefox */
  color: rgb(255, 255, 255);
  background: rgb(145, 145, 145);
}

::selection {
  color: rgb(255, 255, 255);
  background: rgb(145, 145, 145);
}
</style>
