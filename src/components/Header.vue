<template>
  <div class="hello">
    <h3 class="header">{{ msg }}</h3>    
  </div>
</template>

<script>

  export default {
    name: 'Header',
    props: {
      msg: String
    }
  }
  
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

  .header {
    background: #333;
    color: #fff;
    padding: 10px 0;
    margin: 0;
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
