<template>
  <div id="app">
    <navigation></navigation>
    <router-view class="container"/>
    <v-footer></v-footer>
  </div>
</template>

<script>
import Navigation from './components/navigation';
import Footer from './components/footer';


export default {
  name: 'App',
  components: {
    navigation: Navigation,
    'v-footer': Footer,
  },
};
</script>

<style>
  @import '../node_modules/bulma/css/bulma.css';
  @import '../node_modules/bulma-timeline/dist/bulma-timeline.min.css';
  @import '/assets/css/blog.css';
  @import 'https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css';
  @import 'https://fonts.googleapis.com/css?family=Open+Sans';

  @media only screen and (min-width: 1024px) {
    .container {
      width: 1000px !important;
    }
  }
</style>
