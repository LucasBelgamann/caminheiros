<template>
  <div class="background" :class="mode ? 'default-card-color-dark' : 'default-card-color-ligth'">
    <img
      src="https://static.wixstatic.com/media/4f4b22_a6ecbef17b754f1b9397c72e87c8aa3a~mv2.png/v1/fill/w_152,h_140,al_c,q_85,usm_0.66_1.00_0.01,enc_auto/caminheiros-do-bem-png-branco.png"
    />
  </div>
  <div class="form-login">
    <q-input
      class="in-register"
      :class="mode ? 'default-input-color-dark' : 'default-input-color-ligth'"
      clearable
      filled
      color="primary"
      v-model="nome"
      label="Nome"
    />
    <q-input
      class="in-register"
      :class="mode ? 'default-input-color-dark' : 'default-input-color-ligth'"
      clearable
      filled
      color="primary"
      v-model="telefone"
      label="Telefone"
    />
    <q-input
      class="in-register"
      :class="mode ? 'default-input-color-dark' : 'default-input-color-ligth'"
      clearable
      filled
      color="primary"
      v-model="email"
      label="E-mail"
    />
    <q-input
      :type="isPwd ? 'password' : 'text'"
      class="in-register"
      :class="mode ? 'default-input-color-dark' : 'default-input-color-ligth'"
      clearable
      filled
      color="primary"
      v-model="password"
      label="Senha"
    >
      <template v-slot:append>
        <q-icon
          :name="isPwd ? 'visibility_off' : 'visibility'"
          class="cursor-pointer"
          @click="isPwd = !isPwd"
        />
      </template>
    </q-input>
    <q-btn to="/Home" class="login-btn" color="secondary" label="Cadastrar" />
  </div>
  <Footer />
</template>

<script lang="ts">
import { defineComponent } from "vue";
import { ref } from "vue";
import Footer from "src/components/Footer.vue";

export default defineComponent({
  setup() {
    return {
      password: ref(""),
      isPwd: ref(true),
      email: ref(""),
      nome: ref(""),
      telefone: ref(""),
    };
  },
  components: { Footer },
  computed: {
    mode: function () {
      return this.$q.dark.isActive;
    },
  },
});
</script>

<style lang="scss">
.background {
  height: 35vh;
  width: 100vw;
  border-radius: 0 0 50% 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  margin-bottom: 30px;
}

.in-register {
  width: 20vw;
  background-color: #e9edf1;
  margin: 10px 0;
}

.form-login {
  display: flex;
  flex-direction: column;
  align-items: center;
}

.login-btn {
  margin-top: 20px;
  margin-bottom: 40px;
  padding: 10px 35px;
  border-radius: 10px;
}

@media screen and (max-width: 599.99px) {
  .in-register {
    width: 80vw;
  }
}

.default-input-color-ligth {
  background-color: #dbdbdb;
}

.default-input-color-dark {
  background-color: #3b3a3a;
}
</style>
