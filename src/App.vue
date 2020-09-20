<template >
  <main>
      <h2 class='app-title-div'> Wallet - Sua vida financeira em seu controle.</h2>

      <div class='app-main-div'>

          <Carteira :total='total' @enviarVal='total = $event'/>

          <InserirData @enviardados='recebeDados'/>

          <template v-if='dados.length > 0'>
          <ExibirItens :dados='dados'/>
          </template>

          <template v-else>
            <p class='semDadosAdicionados'>Que tal começar a adicionar alguns itens? :)</p>
          </template>

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
      dados: [],
    };
  },
  components: {
    Carteira,
    InserirData,
    ExibirItens,
  },
  methods: {
    recebeDados(informacoes) {
      this.dados.push({
        descricao: informacoes.descricao,
        valor: informacoes.valor,
      });

      this.total -= informacoes.valor;
    },
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

  .semDadosAdicionados{
    margin-top: 20px;
    font-weight: 600;
  }

</style>
