<template>
  <v-container fluid>
    <v-layout column>
      <v-card-title primary-title>
        <div>
          <span class="title">
            Jadwal Praktek
          </span>
        </div>
      </v-card-title>
      <v-container
        grid-list-xl
        fluid
      >
        <v-layout
          row
          align-start
          justify-space-between
        >
          <v-flex
            v-for="({name, url, address}, i) in locations"
            :key="i"
            md4
            offset-xl-1
            xs12
          >
            <map-frame
              :location="url"
              :title="name"
              :address="address"
              :cardHeight="550"
            />
          </v-flex>
        </v-layout>

      </v-container>
    </v-layout>
  </v-container>
</template>

<script lang="ts">
import { Vue, Component } from 'vue-property-decorator';

import MapFrame from '@/components/MapFrame.vue'
import { LocationType } from '@/views/Home.vue';

@Component({
  components: {
    MapFrame
  }
})
class Schedules extends Vue {
  locations: LocationType[] = [
    {
      name: "Kimia Farma",
      url: "https://goo.gl/maps/jzK3giazHCC2",
      address: 'Jl. Jawa, Kartoharjo, Madiun, Kota Madiun, Jawa Timur 63116'
    },
    {
      name: "Al-Hasanah",
      url: "https://goo.gl/maps/tdqFvnk8kVG2",
      address: 'Jl. Sri Rejeki No.91B, Sukosari, Kartoharjo, Kota Madiun, Jawa Timur 63119'
    },
    {
      name: "Rumah",
      url: "https://goo.gl/maps/Rqv3W6u3d572",
      address: 'Jl. Bolodewo'
    }
  ]
}

export default Schedules;
</script>

<style>
</style>
