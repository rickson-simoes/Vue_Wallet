<template>
  <div class='input-valor-descricao'>
    <input type='text' placeholder="Descrição..." v-model='descricao'/>
    <input type='number' placeholder="Valor" v-model='valor'/>
    <button @click="$emit('enviardados', { descricao, valor } )"> Enviar </button>
  </div>
</template>

<script>
export default {
  data() {
    return {
      descricao: '',
      valor: 0,
    };
  },

};
</script>

<style scoped>
  .input-valor-descricao {
    margin-top: 30px;
  }

  .input-valor-descricao input {
    border-style: none;
    margin-bottom: 10px;
    height: 28px;
    width: 250px;
    padding: 10px;
    font-size: 14px;
    font-weight: 300;
    border-radius: 5px;
    margin-right: 10px;
  }

  .input-valor-descricao button {
    border-style: none;
    height: 28px;
    width: 65px;
    border-radius: 2px;
    color: white;
    background: #9293a5;
    font-size:18px;
  }

  .input-valor-descricao button:hover {
    background: #676874;
  }
</style>
