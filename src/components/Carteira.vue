<template>
  <div>
    <span class='carteira-span' >
      Adicione aqui o total que você possui:
      <input type="number" placeholder="Ex.: 800" v-model.number='totalCarteira'/>
      <button @click='enviarValor()'> Enviar </button>
    </span>

    <div class='carteira-valor'>
      Total: {{total}}
    </div>
  </div>
</template>

<script>
export default {
  props: {
    total: {
      type: Number,
      default: 0,
    },
  },
  data() {
    return {
      totalCarteira: 0,
    };
  },
  methods: {
    enviarValor() {
      this.$emit('enviarVal', this.totalCarteira);
    },
  },
};
</script>

<style scoped>
 .carteira-span{
    display: flex;
    align-items: center;

  }

  .carteira-span input{
    border-style: none;
    height: 28px;
    width: 150px;
    padding: 5px;
    font-size: 14px;
    font-weight: 300;
    margin-left: 10px;
  }

  .carteira-span button {
    border-style: none;
    height: 28px;
    width: 65px;
    border-bottom-right-radius: 10px;
    border-top-right-radius: 10px;
    color: white;
    background: #9293a5;
    font-size:18px;
  }

  .carteira-span button:hover {
    background: #777781;
  }

  .carteira-valor {
    margin-top: 30px;
    border-radius: 10px;
    width: fit-content;
    padding: 5px 2px;
  }
</style>
