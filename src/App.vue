<template>
  <div id="app">
    <SelectInter v-on:changeI18n="changeI18n"></SelectInter>
    <HelloWorld/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld'
import SelectInter from './components/SelectInter'
import Vue from 'vue'
import VueI18n from 'vue-i18n'

Vue.use(VueI18n)

// mensagens disponiveis
const messages = {
  en: {
    message: {
      hello: 'Hello World'
    }
  },
  es: {
    message: {
      hello: 'Hola Mundo'
    }
  },

  fr: {
    message: {
      hello: 'Bonjour le monde'
    }
  }
}

const i18n = new VueI18n({
  locale: 'en', // set locale
  messages // set locale messages
})

export default {
  i18n,
  name: 'app',
  components: {
    HelloWorld,
    SelectInter
  },
  methods: {
    // método responsavel por mudar a internacionalizaçao do APP
    changeI18n: function (language) {
      i18n.locale = language
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
</style>
