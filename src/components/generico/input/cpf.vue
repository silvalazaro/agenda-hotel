<template>
  <q-input
    filled
    v-model="cpf"
    label="CPF"
    hint="Nome"
    class="q-mt-md"
    placeholder="CPF"
  />
</template>

<script>
export default {
  props: {
    cpf: {
      type: String
    }
  }
}
</script>
