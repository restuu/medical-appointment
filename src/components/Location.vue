<template>
  <div>
    <a
      :href="locationUrl"
      :class="`headline ${color}--text`"
      target="_blank"
    >
      <v-icon :color="color">
        place
      </v-icon>{{ locationName }}
    </a>
  </div>
</template>

<script lang="ts">
import { Vue, Component, Prop } from "vue-property-decorator";

@Component
export default class Location extends Vue {
  @Prop()
  locationName!: string;
  @Prop()
  locationUrl!: string;
  @Prop({ default: "black" })
  color!: string;
}
</script>
