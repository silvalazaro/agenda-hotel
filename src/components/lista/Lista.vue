<template>
  <q-table
    title="Usuários"
    row-key="nome"
    selection="single"
    :selected.sync="selected"
    :columns="getColumns()"
    :data="data"
    :filter="filter"
    flat
    bordered
  >
  <!-- Pesquisar -->
   <template v-slot:top-right>
        <q-input borderless dense debounce="300" v-model="filter" placeholder="Pesquisar">
          <template v-slot:append>
            <q-icon name="search" />
          </template>
        </q-input>
      </template>
  </q-table>
</template>

<script lang="ts">
import { FieldColumn } from 'components/models'
export default {
  // name: 'ComponentName',
  props: ['columns', 'data'],
  data () {
    return {
      selected: [],
      filter: ''
    }
  },
  created: function () {
    // console.log(this.columns[0].name)
  },
  methods: {
    getColumns () {
      if (this.columns) {
        const cols: FieldColumn[] = []
        this.columns.forEach(field => {
          cols.push(this.getColumn(field))
        })
        return cols
      }
    },
    getColumn: (field: FieldColumn) => {
      const coluna = {
        name: field.name,
        label: field.label,
        field: field.name,
        sortable: true
      }
      return coluna
    }
  }
}
</script>
