<template>
  <div id="app">
    <h1>Word search</h1>

    <section v-if="tela === 'inicio'" id="inicio">
      <MeuFormulario
        v-if="etapa === 'palavra'"
        title="Defina a palavra"
        button="Proximo"
        :action="setPalavra"
      />

      <MeuFormulario
        v-if="etapa === 'dica'"
        title="Defina a dica"
        button="Iniciar"
      />
    </section>
    <section v-if="tela === 'jogo'" id="jogo">Jogo</section>
  </div>
</template>

<script>
import MeuFormulario from "./components/Formulario.vue";
import "./css/global.css";

export default {
  name: "App",
  data() {
    return {
      tela: "inicio",
      etapa: "palavra",
    };
  },
  components: {
    MeuFormulario,
  },
  methods: {
    setPalavra: function (palavra) {
      alert(palavra);
    },
  },
};
</script>

<style>
#app {
  width: 100%;
  height: 100%;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
}
</style>
