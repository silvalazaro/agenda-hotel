<template>
  <div ref="form">
    <q-form class="q-gutter-md">
      <div v-for="(campo, key) in getComponentes()"  :key="campo.key">
          <component
          :is="campo"
          v-bind="getConfigComponents[key]"
        ></component>
      </div>
    </q-form>

  </div>
</template>

<script>
import { QInput } from 'quasar'
export default {
  // name: 'ComponentName',
  props: ['atributos'],
  data () {
    return {
      configCampos: [{
        label: 'Lazaro'
      }]
    }
  },
  methods: {
    getComponentFromField (atributo) {
      let component
      switch (atributo.type) {
        case 'int':
        case 'boolean':
        default:
          component = 'q-input'
      }
      return component
    },
    getConfigComponentFromField (atributo) {
      return {
        label: atributo.name
      }
    },
    getComponentes () {
      const campos = []
      this.atributos.forEach(element => {
        campos.push(this.getComponentFromField(element))
      })
      return {
        'q-input': {
          label: 'Lazaro  '
        }
      }
    },
    getConfigComponents (key) {
      console.log(key)
      return this.getConfigComponentFromField(this.atributos[key])
    }
  }
}
</script>
