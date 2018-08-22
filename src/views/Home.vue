<template>
  <v-container fluid>
    <v-slide-y-transition mode="out-in">
      <v-parallax
        src="https://parkersquaremedical.com/wp-content/uploads/2015/08/ThinkstockPhotos-126930170-e1440532560232.jpg"
        height="1000"
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

<script>
import Location from '@/components/Location';

export default {
  components: {
    Location
  },
  data() {
    return {
      locations: [
        {
          name: 'Kimia Farma',
          url: 'https://www.google.com/maps/place/Kimia+Farma+Apotik/@-7.62351,111.5199933,17z/data=!3m1!4b1!4m5!3m4!1s0x2e79be57e94a6105:0x18abcd998e793463!8m2!3d-7.62351!4d111.522182'
        },
        {
          name: 'Al-Hasanah',
          url: 'https://www.google.com/maps/place/Mother+%26+Child+Hospital+Al+Hasanah/@-7.6192911,111.5299875,17z/data=!3m1!4b1!4m5!3m4!1s0x2e79befb7ecb7e9b:0xa3cda995e90b27de!8m2!3d-7.6192911!4d111.5321816'
        }
      ]
    }
  }
}
</script>
