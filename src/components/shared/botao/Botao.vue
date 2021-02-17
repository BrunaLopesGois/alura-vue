<template>
  <button @click="disparaAcao()" class="botao" :class="estiloDoBotao" :type="tipo">{{ rotulo }}</button>
</template>

<script>
// ["tipo", "rotulo", "confirmacao", "estilo"]
export default {
  props: {
    tipo: {
      required: true,
      type: String,
    },
    rotulo: {
      required: true,
      type: String,
    },
    confirmacao: Boolean,
    estilo: String,
  },

  methods: {
    disparaAcao() {
      if (this.confirmacao) {
        if (confirm("Deseja realmente remover a foto?")) {
          this.$emit("botaoAtivado");
          return;
        }
      }
      this.$emit("botaoAtivado");
    },
  },

  computed: {
    estiloDoBotao() {
      if (this.estilo == "padrao" || !this.estilo) return "botao-padrao";
      if (this.estilo == "perigo") return "botao-perigo";
    },
  },
};
</script>

<style scoped lang="sass">
@import './Botao.scss'
</style>
