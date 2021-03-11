<template>
  <section class="consultoria-section">
    <div class="consultoria-section__container">
      <h2 class="consultoria-section__title">Pronto para planejar seu sossego?</h2>
      <p class="consultoria-section__text">Agende uma consultoria sem compromisso pelo formulário abaixo!</p>
      <form action="#" @submit.prevent="handleForm">
        <input-group id="nome1" v-model="inputNome" type="text" label="Nome:" />
        <input-group id="email1" v-model="inputEmail" type="email" label="E-mail:" />
        <input-group id="estadoCivil1" v-model="inputEstadoCivil" type="text" label="Estado Civil:" />
        <input-group id="profissao1" v-model="inputProfissao" type="text" label="Profissão:" />
        <input-group id="telefone1" v-model="inputTelefone" type="text" label="Telefone/Whatsapp:" />
        <input-group id="renda1" v-model="inputRenda" type="text" label="Renda Mensal:" />
        <div class="consultoria-section__cta">
          <base-button type="submit" :is-rounded="true">Enviar</base-button>
        </div>
      </form>
    </div>
  </section>
</template>

<script>
import InputGroup from './InputGroup';
import BaseButton from './BaseButton';

export default {
  name: 'ConsultoriaSection',
  components: {
    InputGroup,
    BaseButton
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
.consultoria-section {
  width: 100%;
  max-width: 880px;

  margin-top: 25px;
  padding: var(--default-padding);
  
  display: none;
}

.consultoria-section__container {
  padding: var(--default-padding);

  background-color: var(--blue);
  color: var(--white);
}

.consultoria-section .consultoria-section__cta {
  width: 100%;
  margin-top: 30px;

  text-align: center;
}

@media (max-width: 768px) {
  .consultoria-section {
    display: block;
  }
}
</style>