<template>
  <div id="app">
   <button @click.prevent="pay">Pay</button>
  </div>
</template>

<script>
export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
      paylike: null
    }
  },

  created () {
   this.paylike = Paylike('04d25ce0-52c3-40bd-9f66-8951910e44d4');
  },

  methods: {
    pay () {
      this.paylike.popup({
        currency: 'DKK',
        amount: 19995,
      }, function( err ){
        if (err)
          return console.warn(err);

      console.log(r); // { transaction: { id: ... } }

      location.href = '/thank-you';
    });
    }
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
