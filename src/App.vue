<template>
  <div v-for="index in list" v-bind:key="index" class="card">
    <div>
    <input
      type="text"
      id="username"
      name="username"
      v-model="index.username"
      placeholder="Username"
    />
    <input
      type="email"
      id="email"
      name="email"
      v-model="index.email"
      placeholder="Email"
    />

    </div>
    <button v-on:click="add()">Add</button>
    <button v-on:click="remove(index)" id="remove">Remove</button>


    <!-- <p v-for="user in list" v-bind:key="user" ref="user">
      UserName: {{ user.username }} <br />
      Email: {{ user.email }}
    </p> -->
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      list: [{
        username: "",
        email: ""
      }],
    };
  },

  methods: {
    add: function () {
      this.list.push({
        username:"" ,
        email: ""
      });
    },
    remove: function (index) {
      this.list.splice(this.list.indexOf(index), 1);
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
.card {
  background-color: #ecf0f1;
  border-radius: 4px;
  margin: 0 auto;
  padding: 0 20px 20px;
  width: 360px;
  margin-top: 20px;
}
input {
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-size: 1em;
  padding: 10px;
  margin: 10px 5px;
  border: 0;
  border-bottom: 1px solid #757575;
}
button {
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  font-size: 1em;
  padding: 10px;
  margin: 10px 5px;
  border: 0;
  border-radius: 3px;
  background-color: #3498db;
  color: #ecf0f1;
}
#remove {
  background-color: #e74c3c;
}
</style>
