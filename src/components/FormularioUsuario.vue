<template>
  <q-form
    action="https://some-url.com"
    method="post"
  >
    <input-cpf cpf="cpf">
    </input-cpf>
  </q-form>
</template>

<script>
import inputCpf from './generico/input/cpf.vue'
export default {
  // name: 'ComponentName',
  components: {
    inputCpf
  }
}
</script>
