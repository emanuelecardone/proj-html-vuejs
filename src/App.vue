<template>
  <!--IMPORTANTE: 
  Per questioni di spazio e dopo 2 ticket a riguardo riprodurrò il layout per una dimensione di 1920 px di larghezza (come da screenshot) -->
  <div id="app">
    <Header :upData="headerData" />
    <Main />
    <Footer />
    <ToolsBox />
  </div>
</template>

<script>
import Header from './components/Header.vue';
import Main from './components/Main.vue';
import Footer from './components/Footer.vue';
import ToolsBox from './components/ToolsBox.vue';

export default {
  name: "App",
  components: {
    Header,
    Main,
    Footer,
    ToolsBox
  },
  data: function(){
    return {
      // Oggetto con la struttura dati per l'header superiore (l'header inferiore non ha dati ripetuti, quindi sarà statico)
      headerData: {
        links: ['courses', 'zoom', 'pages', 'bundles', 'course formats', 'add course', 'demos'],
        newIndexes: [1,5],
        socials: ['twitter', 'instagram', 'behance', 'dribbble', 'flickr', 'git', 'linkedin', 'pinterest']
      },
      // Oggetto con la struttura dati per il footer
      footerData: {
        about: {
          name: 'about',
          text1: 'Masterstudy is Education WordPress theme featured by Learning Management System (LMS) for online education.',
          text2: 'Developed by StylemixThemes.',
          icons: ['facebook', 'twitter', 'instagram']
        },
        contact: {
          name: 'contact',
          address: 'USA, California 20, First Avenure, California',
          numberContacts: [
            {
              name: 'Tel.',
              number: '+1 212 458 300 32'
            },
            {
              name: 'Fax',
              number: '+1 212 375 24 14'
            }
          ],
          email: 'info@masterstudy.com'
        },
        pages: {
          name: 'pages',
          pages: ['blog', 'home', 'shortcodes', 'courses', 'membership a...', 'typography']
        },
        blog: {
          name: 'blog',
          blogs: [
            {
              image: 'photo-1517520287167-4bbf64a00d66-122x120',
              text: 'Our main target is to "Developing Yourself as a Leader"',
              date: 'August 9, 2018'
            },
            {
              image: 'photo-1490376840453-5f616fbebe5b-122x120',
              text: 'Those Other College Expenses You Aren\'t Thinking About',
              date: 'June 3, 2015'
            }
          ]
        }
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
