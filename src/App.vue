<template >
  <main>
      <h2 class='app-title-div'> Wallet - Sua vida financeira em seu controle.</h2>

      <div class='app-main-div'>

          <Carteira :total='total' @enviarVal='total = $event'/>

          <InserirData/>

          <ExibirItens :dados='dados'/>

      </div>
  </main>
</template>

<script>
import Carteira from './components/Carteira.vue';
import InserirData from './components/InserirData.vue';
import ExibirItens from './components/ExibirItens.vue';

export default {
  data() {
    return {
      total: 0,
      dados: [
        { descricao: 'teste', valor: 10 },
      ],
    };
  },
  components: {
    Carteira,
    InserirData,
    ExibirItens,
  },
};
</script>

<style>
  main {
    margin-top: 40px;
  }

  .app-title-div {
    margin: 10px;
  }

  .app-main-div {
    top: 50px;
    position: relative;
    width: 750px;
    height: auto;
    left: 50px;
  }

</style>
