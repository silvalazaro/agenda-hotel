<template>
  <q-card
    flat
    bordered
  >
    <q-img src="https://cdn.quasar.dev/img/parallax1.jpg">
    </q-img>
    <q-card-section>
      <div class="text-h5">
        Maria Comedoria
      </div>
      <div>
        <q-rating
          size="2em"
          :max="5"
          color="primary"
          :value="3"
        />
        - 5.3km
      </div>
    </q-card-section>
    <q-card-section horizontal>
      <q-btn
        flat
        color="primary"
        icon="phone"
        class="full-width"
        size="lg"
      />

      <q-btn
        flat
        color="primary"
        icon="access_time"
        class="full-width"
        size="lg"
      />
      <q-btn
        flat
        color="primary"
        icon="directions"
        class="full-width"
        size="lg"
      />
    </q-card-section>
    <q-img src="https://cdn.quasar.dev/img/parallax2.jpg" />

    <q-list>
      <q-item clickable>
        <q-item-section avatar>
          <q-icon
            color="primary"
            name="location_on"
          />
        </q-item-section>

        <q-item-section>
          <q-item-label>Bar XYZ</q-item-label>
          <q-item-label>Have a drink.</q-item-label>
        </q-item-section>
      </q-item>

      <q-item clickable>
        <q-item-section avatar>
          <q-icon
            name="phone"
          />
        </q-item-section>

        <q-item-section>
          <q-item-label>(82) 98835-6504</q-item-label>
        </q-item-section>
      </q-item>

      <q-item clickable>
        <q-item-section avatar>
          <q-icon
            name="language"
          />
        </q-item-section>
        <q-item-section>
          <q-item-label>https://www.tekcerto.com.br</q-item-label>
        </q-item-section>
      </q-item>
    </q-list>
  </q-card>
</template>

<script>
export default {
  // name: 'ComponentName',
  data () {
    return {}
  }
}
</script>
