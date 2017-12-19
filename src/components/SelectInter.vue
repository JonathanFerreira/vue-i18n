<template>
  <div id="header">
    <select v-model="selected" v-on:change="emitChangeI18n">
      <option disabled value="">Escolha um internacionalização</option>
      <option value="en">Inglês</option>
      <option value="es">Espanhol</option>
      <option value="fr">Francês</option>
    </select>
    <br>
    <span>Selecionado: {{ selected }}</span>
  </div>
</template>

<script>
  export default {
    name: 'LocaleHeader',
    data () {
      return {
        selected: ''
      }
    },
    methods: {
      // metódo que captura a linguagem seleciona e emit
      // o event para o componente pai
      emitChangeI18n: function () {
        this.$emit('changeI18n', this.selected)
      }
    }
  }
</script>
