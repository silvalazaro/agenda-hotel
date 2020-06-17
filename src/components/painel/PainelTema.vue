<template>
  <div>
    <q-card flat>
      Escolha um tema de seu interesse
      <q-card-section horizontal>
          <q-img  v-for="(tema, index)  in temas" :key="index"
            class="col-5 q-mr-sm"
            :src="tema.imagem"
          >
            <div class="absolute-full text-subtitle2 flex flex-center">
              {{tema.texto}}
            </div>
          </q-img>
      </q-card-section>
    </q-card>
  </div>
</template>

<script>
import { mapState } from 'vuex'
export default {
  // name: 'ComponentName',
  data () {
    return {}
  },
  computed: mapState({
    temas: state => state.listaTema.lista
  })
}
</script>
