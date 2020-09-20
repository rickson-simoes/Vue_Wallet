<template>
  <div class="input-valor-descricao">
    <input type="text" placeholder="Descrição..." v-model="descricao" :class="{error, noerror}" />
    <input type="number" placeholder="Valor" v-model="valor" :class="{error, noerror}"/>
    <button @click="enviarDados()">Enviar</button>

    <template v-if="error"> <div class='errorMsg'>Por favor, inserir descrição e valor válidos.</div> </template>
  </div>
</template>

<script>
export default {
  data() {
    return {
      descricao: '',
      valor: '',
      error: false,
      noerror: true,
    };
  },
  methods: {
    enviarDados() {
      if (this.descricao === '' || this.valor <= 0) {
        this.error = true;
        this.noerror = false;

        return;
      }
      this.$emit('enviardados', {
        descricao: this.descricao,
        valor: this.valor,
      });

      this.error = false;
      this.noerror = true;
    },
  },
};
</script>

<style scoped>
.input-valor-descricao {
  margin-top: 30px;
  display: flex;
}

.input-valor-descricao input {
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
  width: 85px;
  border-radius: 2px;
  color: white;
  background: #9293a5;
  font-size: 18px;
}

.input-valor-descricao button:hover {
  background: #676874;
}

.error {
  background-color: rgb(231, 198, 198);
  border: 1px solid rgb(182, 4, 4);
}

.errorMsg {
    position: absolute;
    top: 90px;
    background: #b43b3b;
    width: fit-content;
    padding: 5px;
    border-radius: 20px;
    text-align: center;
    color: white;
    left: 130px;
    font-weight: 200;
    font-size: 14px;
}

.noerror {
  border: none;
}
</style>
