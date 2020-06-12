<template>
  <div class="q-pa-md">
    <div
      class="q-gutter-y-md rounded-borders"
      style="max-width: 400px"
    >
      <div class="text-h4 text-center">
        Entrar
      </div>
      <q-form
        action="https://some-url.com"
        method="post"
      >
        <q-input
          filled
          v-model="nome"
          label="Usuário"
          hint="Nome de usuário ou e-mail"
          class="q-mt-md"
        />
        <q-input
          type="password"
          filled
          v-model="senha"
          label="Senha"
          class="q-mt-md"
        />
        <q-btn
          label="Confirmar"
          type="submit"
          color="primary"
          class="fit q-mt-md"
        />
      </q-form>
    </div>
    <q-btn
      flat
      label="Esqueceu sua senha?"
      class="q-mt-md"
    />
    <q-btn
      flat
      label="Realizar cadastro"
      class="q-mt-md"
    />
  </div>
</template>

<script>
import { computed } from '@vue/composition-api'
export default {
  // name: 'ComponentName',
  computed: {
    nome () {
      return this.$store.state.usuario.nome
    },
    senha () {
      return this.$store.state.usuario.senha
    }
  }
}
</script>
