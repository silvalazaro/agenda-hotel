<template>
  <q-page padding>
    <lista :columns="columns" :data="usuarios">
    </lista>
  </q-page>
</template>

<script lang='ts'>
import lista from 'components/lista/Lista.vue'
import { Usuario } from 'components/models'
export default {
  // name: 'PageName',
  components: {
    lista
  },
  data () {
    const usuarios: Usuario[] = [{
      id: 1,
      nome: 'Usuario Teste 1',
      ativo: true,
      versao: 1
    }, {
      id: 2,
      nome: 'Usuario Teste 2',
      ativo: false,
      versao: 2
    }]
    return {
      usuarios,
      columns: [{
        name: 'id',
        label: 'Id'
      }, {
        name: 'nome',
        label: 'Nome'
      }, {
        name: 'ativo',
        label: 'Ativo'
      }, {
        name: 'versao',
        label: 'Versao'
      }]
    }
  }
}
</script>
