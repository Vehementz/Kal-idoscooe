<template>
  <h1>Kaléidoscope</h1>
  <img :class="gender" v-bind:src="picture" alt="Vue logo" >
  <h2>{{ lastName }} {{  firstName  }} </h2>

  <button v-on:click="getUSer()">See an other person</button>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      gender: "male",
      logmessage: "hello world",
      firstName: "Smith",
      lastName: "Camille",
      email: "guhrir@gmail.com",
      picture: "https://images.unsplash.com/photo-1661961110671-77b71b929d52?ixlib=rb-4.0.3&ixid=MnwxMjA3fDF8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=870&q=80"
    }
  },
  components: {},
  methods: {

      async getUSer() {
      
        const res = await fetch("https://randomuser.me/api");
        const { results } = await res.json();
        console.log(results);
      
      this.firstName = results[0].name.first,
      this.lastame = "Smoth",
      this.email = "yoyo@gmail.com",
      this.gender = "male",
      this.picture = results[0].picture.large
  },
    },
  }

</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #6b8eb1;
  margin-top: 60px;
}

.male {
  border-radius: 555555555px;
  border: 5px solid black;
  width: 5rem;
  height: 5rem;
}
</style>
