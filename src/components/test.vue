<template>
  <div class="test">
    <input type="text" v-model="title"><br />
    <h1> {{ title }}</h1>
    <p v-if="showName"> {{user.first_name}} </p>
    <p v-else="showName"> Please login... </p>
    <ul>
        <li v-for="item in items"> {{item.title}} </li>
    </ul>
    <button v-on:click="greet(title)"> Say Greet </button>
    <br />
    <input type="text" v-on:keyup="pressKey" v-on:keyup.enter="enterHit">
    <hr>
    <label> First Name </label> <input type="text" v-model="user.first_name">
    <br>
    <label> Last Name </label> <input type="text" v-model="user.last_name">
    <h3> {{fullname}} </h3>
    <h2> {{msg}} </h2>
  </div>
</template>

<script>
  export default {
    name: 'test',
    props: {
      msg: {
        type: String,
        default: 'Foobar'
      }
    },
    data () {
      return {
        title: "<h1> Hello World </h1>",
        user: {
          first_name: 'John',
          last_name: 'Doe'
        },
        showName: true,
        items: [ {title: 'Item One'}, {title: 'Item Two'} ]
      }
    },
    methods: {
      greet: function(title)
      {
        var len =  "Test";
        alert('Hello: ' + title);
      },
      pressKey: function(e)
      {
        console.log(e.target.value);
      },
      enterHit: function()
      {
        console.log("You git enterl");
      }
    },
    computed:
    {
      fullname: function()
      {
        return this.user.first_name + ' ' + this.user.last_name;
      }
    }
  }
</script>

<style scoped>

</style>
