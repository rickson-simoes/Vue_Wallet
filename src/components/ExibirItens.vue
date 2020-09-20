<template>
  <div class="exibir-itens">
    <div class="descricao-itens">
      <span>Descrição</span>
      <span>Valor</span>
    </div>

    <div class="lista-itens" v-for="(dado, i) in dados" :key='i'>
      <span>{{dado.descricao}}</span>
      <span>{{dado.valor}}</span>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    dados: {
      type: Array,
    },
  },
};
</script>

<style scoped>
.exibir-itens {
  margin-top: 30px;
  display: flex;
  flex-direction: column;
}

.descricao-itens {
  display: flex;
}

.descricao-itens span:first-child {
  border-right: 1px solid #797676;
  border-top-left-radius: 10px;
}

.descricao-itens span:nth-child(2) {
  border-top-right-radius: 10px;
}

.descricao-itens span {
  font-weight: 800;
  align-content: center;
  background: #9293a5;
  width: 300px;
  height: 50px;
  display: flex;
  justify-content: center;
  align-items: center;
}

.lista-itens span:first-child {
  border-right: 1px solid #4d4c4c;
}

.lista-itens span {
  background: #d4d3d3;
  display: table-cell;
  width: 300px;
  padding: 15px;
  word-break: break-all;
  color: #5e5b5b;
  vertical-align: middle;
  text-align: center;
}

.lista-itens:not(:last-child) span {
  border-bottom: 1px solid black;
}
</style>
