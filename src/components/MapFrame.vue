<template>
  <v-card :height="cardHeight">
    <div>
      <iframe
        width="100%"
        height="300"
        :src="'https://maps.google.com/maps?width=100%&amp;height=200&amp;hl=en&amp;coord=-7.62351,111.5199933&amp;q=Jl.%20Jawa%2C%20Kartoharjo%2C%20Madiun%2C%20Kota%20Madiun%2C%20Jawa%20Timur%2063116+(Kimia%20Farma)&amp;ie=UTF8&amp;t=&amp;z=14&amp;iwloc=B&amp;output=embed'"
        frameborder="0"
        scrolling="no"
        marginheight="0"
        marginwidth="0"
      />
    </div>
    <v-card-title>
      <div>
        <h2>{{ title }}</h2>
      </div>
    </v-card-title>
    <v-card-text>
      <div>
        <!-- <span class="text-detail">
          <strong>Address:</strong> {{ address || '&zwnj;' }}</span>
        <span class="text-detail">Telp: {{ contact || '&zwnj;' }}</span> -->
        <table>
          <tr>
            <th class="text-top-left">Address:</th>
            <td>{{ address || '&zwnj;' }}</td>
          </tr>
          <tr>
            <th class="text-top-left">Telp:</th>
            <td>{{ contact || '&zwnj;' }}</td>
          </tr>
        </table>
      </div>
    </v-card-text>
    <v-card-actions>
      <v-btn
        color="primary"
        @click="console.log('a')"
      >Click</v-btn>
    </v-card-actions>
  </v-card>
</template>

<script lang="ts">
import { Vue, Component, Prop } from 'vue-property-decorator'

@Component
class MapFrame extends Vue {
  @Prop() location!: string;
  @Prop() title!: string;
  @Prop({ default: '100%' }) width!: string;
  @Prop() address?: string;
  @Prop() contact?: string;
  @Prop() cardHeight?: number;

}

export default MapFrame;
</script>

<style>
.text-detail {
  display: block;
}
th.text-top-left {
  vertical-align: top;
  text-align: left;
}
</style>

