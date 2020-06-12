<template>
  <div>
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
        <q-btn
          color="primary"
          flat
          icon="add"
          @click="formulario = true"
        />
        <q-input
          borderless
          dense
          debounce="300"
          v-model="filter"
          placeholder="Pesquisar"
        >
          <template v-slot:append>
            <q-icon name="search" />
          </template>
        </q-input>
      </template>
    </q-table>
    <!-- Formulario de cadastro-->
    <q-dialog v-model="formulario">
      <q-card>
        <q-card-section>
          <div class="text-h6">Cadastro</div>
        </q-card-section>
        <q-card-section class="q-pt-none">
          <formulario :fields="fields">
          </formulario>
         </q-card-section>
        <q-card-actions align="right">
          <q-btn
            flat
            label="OK"
            color="primary"
            v-close-popup
          />
        </q-card-actions>
      </q-card>
    </q-dialog>
  </div>
</template>

<script lang="ts">
import Formulario from 'components/formulario/Formulario.vue'
import { FieldColumn } from 'components/models'
export default {
  // name: 'ComponentName',
  components: {
    Formulario
  },
  props: ['columns', 'data'],
  data () {
    return {
      selected: [],
      filter: '',
      formulario: false,
      fields: ['cpf']
    }
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
