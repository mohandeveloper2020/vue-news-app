<template>
  <div id="app">    
    <Header msg="Welcome to Vue news app"/>
    <NewsList />
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header';
import NewsList from './components/NewsList';
import Footer from './components/Footer';

export default {
  name: 'app',
  components: {
    Header,
    NewsList,
    Footer
  }
}
</script>

<style>
  body {
    margin: 0;
  }
  
  #app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialiased;
    -moz-osx-font-smoothing: grayscale;
    text-align: center;
    color: #2c3e50;
  }
</style>
