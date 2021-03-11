<template>
  <div class="hero-form">
    <h2 class="hero-form__title">Pronto para planejar seu sossego?</h2>
    <p class="hero-form__text">Agende uma consultoria sem compromisso pelo formulário abaixo!</p>
    <form action="#" @submit.prevent="handleForm">
      <input-group id="nome" v-model="inputNome" type="text" label="Nome:" />
      <input-group id="email" v-model="inputEmail" type="email" label="E-mail:" />
      <input-group id="estadoCivil" v-model="inputEstadoCivil" type="text" label="Estado Civil:" />
      <input-group id="profissao" v-model="inputProfissao" type="text" label="Profissão:" />
      <input-group id="telefone" v-model="inputTelefone" type="text" label="Telefone/Whatsapp:" />
      <input-group id="renda" v-model="inputRenda" type="text" label="Renda Mensal:" />
      <div class="hero-form__cta">
        <base-button type="submit" :is-rounded="true">Enviar</base-button>
      </div>
    </form>
  </div>
</template>

<script>
import BaseButton from './BaseButton'
import InputGroup from './InputGroup'

export default {
  name: 'HeroForm',
  components: {
    BaseButton,
    InputGroup
  },
  data () {
    return {
      inputNome: '',
      inputEmail: '',
      inputEstadoCivil: '',
      inputProfissao: '',
      inputTelefone: '',
      inputRenda: ''
    }
  },
  methods: {
    handleForm: function () {
      alert(`Olá ${this.inputNome}, obrigado pelo interesse, em breve entraremos em contato.`)
    }
  }
}
</script>

<style scoped>
.hero-form {
  width: 100%;
  height: fit-content;

  padding: .4rem var(--default-padding) 1.8rem var(--default-padding);

  background-color: var(--blue);
  color: var(--white);
}

.hero-form__title {
  margin-bottom: 30px;
}

.hero-form__text {
  margin-bottom: 30px;
}

.hero-form .hero-form__cta {
  width: 100%;
  margin-top: 30px;

  text-align: center;
}
</style>