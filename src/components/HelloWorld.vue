<template>
  <v-container>
    <center>
      <v-card
        v-for="index in list"
        v-bind:key="index"
        elevation="3"
        class="card"
      >
        <div class="subtitle">
          <v-text-field
            label="Username"
            type="text"
            id="username"
            name="username"
            v-model="index.username"
          />
          <v-text-field
            label="Email"
            type="email"
            id="email"
            name="email"
            v-model="index.email"
          />
        </div>
        <v-card-actions>
        <v-spacer></v-spacer>
        <v-btn @click="add()" color="accent">Add</v-btn>
        <v-spacer></v-spacer>
        <v-btn @click="remove(index)" color="error">Remove</v-btn>
        <v-spacer></v-spacer>

      </v-card-actions>
     
        <!-- <p v-for="user in list" v-bind:key="user" ref="user">
      UserName: {{ user.username }} <br />
      Email: {{ user.email }}
    </p>  -->
      </v-card>
    </center>
  </v-container>
</template>

<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      list: [
        {
          username: "",
          email: "",
        },
      ],
    };
  },

  methods: {
    add: function () {
      this.list.push({
        username: "",
        email: "",
      });
    },
    remove: function (index) {
      this.list.splice(this.list.indexOf(index), 1);
    },
  },
};
</script>

<style>
.subtitle {
  padding: 1% 20%;
  align-items: center;
}
.card {
  width: 40%;
  margin: 20px 20px;

}
</style>