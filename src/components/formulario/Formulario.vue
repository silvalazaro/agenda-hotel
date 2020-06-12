<template>
  <div>
    <q-form class="q-gutter-md">
      <q-input
        filled
        label="Seu nome"
      />
    </q-form>

  </div>
</template>

<script>
import { QInput } from 'quasar'
export default {
  // name: 'ComponentName',
  props: ['fields'],
  data () {
    return {}
  },
  methods: {
    getField () {
      return new QInput()
    }
  },
  created () {
    let a
  }
}
</script>
