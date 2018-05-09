<template>
  <div id="app" class="container">
    <img src="./assets/logo.png">
    <app-header :quotes="quotes" :max-quotes="maxQuotes" />
    <app-new-quote v-if="quotes.length < 10" v-on:addNewQuote="addQuote" />
    <app-list v-bind:quotes="quotes" @deleteQuote="deleteQuote" />
  </div>
</template>

<script>
import List from './components/List.vue';
import NewQuote from './components/NewQuote.vue';
import Header from './components/Header.vue';

export default {
  name: 'app',
  components: {
    appList: List,
    appNewQuote: NewQuote,
    appHeader: Header
  },
  data() {
    return {
      quotes: [
        'test quote',
      ],
      maxQuotes: 10
    };
  },
  methods: {
    addQuote(quote) {
      this.quotes.push(quote);
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1);
    }
  }
}
</script>

<style lang="scss">
@import '../node_modules/bootstrap/scss/bootstrap.scss';
@import '../styles.scss';

#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
