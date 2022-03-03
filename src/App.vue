<template>
  <input type="text" id="username" name="username" v-model="username" placeholder="Username" />
  <br />
  <br />
  <input type="email" id="email" name="email" v-model="email" placeholder="Email"/>
  <br />
  <br />
  <button v-on:click="getData()">Submit</button>
  <br />
  <br />
  <div>
    <p v-for="user in list" v-bind:key="user" ref="user"> UserName: {{user.username}} <br> Email: {{user.email}}</p> 
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      list: [],
      username: '',
      email: ''
    };
  },

  methods: {
    getData: function () {
      this.list.push({
        username :this.username ,
        email : this.email

      })
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
