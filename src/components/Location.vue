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

<script>
export default {
  props: {
    locationName: String,
    locationUrl: String,
    color: {
      type: String,
      default: 'black'
    }
  }
}
</script>
