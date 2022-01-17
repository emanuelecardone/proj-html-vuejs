<template>
  <div id="app">
    <Header :upData="headerData" />
    <Main />
    <Footer />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Main from './components/Main.vue';
import Footer from './components/Footer.vue';

export default {
  name: "App",
  components: {
    Header,
    Main,
    Footer
  },
  data: function(){
    return {
      // Oggetto con la struttura dati per l'header superiore (l'header inferiore non ha dati ripetuti, quindi sarà statico)
      headerData: {
        links: ['courses', 'zoom', 'pages', 'bundles', 'course formats', 'add course', 'demos'],
        newIndexes: [1,5],
        socials: ['twitter', 'instagram', 'behance', 'dribbble', 'flickr', 'git', 'linkedin', 'pinterest']
      }
    };
  }
};
</script>

<style lang="scss">
@import './style/variables.scss';
@import './style/mixins.scss';
@import './style/general.scss';
@import './style/size-space.scss';
@import './style/utilities.scss';

</style>
