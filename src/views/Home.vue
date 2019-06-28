<template>
  <v-container fluid>
    <v-slide-y-transition mode="out-in">
      <v-parallax
        src="https://parkersquaremedical.com/wp-content/uploads/2015/08/ThinkstockPhotos-126930170-e1440532560232.jpg"
        height="600"
        alt="preview"
      >
        <v-layout
          column
          align-end
          class="white--text"
        >
          <div class="display-3">
            Wellcome
          </div>
          <location
            v-for="location in locations"
            :key="location.name"
            :locationUrl="location.url"
            :locationName="location.name"
            color="white"
            class="mb-2"
          />
        </v-layout>
      </v-parallax>
    </v-slide-y-transition>
  </v-container>
</template>

<script lang="ts">
import { Component, Vue } from "vue-property-decorator";
import Location from "@/components/Location.vue";

export type LocationType = {
  name: string;
  url: string;
  address: string;
};

@Component({
  components: {
    Location
  }
})
export default class Home extends Vue {
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
  ];
}
</script>
