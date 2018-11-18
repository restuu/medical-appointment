<template>
  <v-app>
    <v-navigation-drawer
      persistent
      :clipped="true"
      width="200"
      v-model="drawer"
      disable-resize-watcher
      fixed
      app
      class="hidden-md-and-up"
    >
      <v-list>
        <v-list-tile
          value="true"
          v-for="(item, i) in items"
          :key="i"
          :to="{name: item.target}"
        >
          <v-list-tile-action>
            <v-icon v-html="item.icon"/>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title v-text="item.title"/>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar
      app
      :clipped-left="true"
    >
      <v-toolbar-side-icon
        @click.stop="drawer = !drawer"
        class="hidden-md-and-up"
      />
      <v-toolbar-title
        v-text="title"
        @mouseover="titleHover = true"
        @mouseout="titleHover = false"
        @click="linkTo('home')"
        :class="{ pointer: titleHover }"
      />
      <v-spacer/>
      <v-toolbar-items class="hidden-sm-and-down">
        <v-btn 
          v-for="(item, i) in items"
          :key="i"
          flat
          v-text="item.title"
          append
          @click="linkTo(item.target)"
        />
      </v-toolbar-items>
    </v-toolbar>
    <v-content>
      <router-view/>
    </v-content>
    <v-footer fixed app>
      <span>&copy; 2017</span>
    </v-footer>
  </v-app>
</template>

<script lang="ts">
import { Vue, Component } from "vue-property-decorator";

@Component
export default class App extends Vue {
  drawer: boolean = false;
  items = [
    {
      icon: "bubble_chart",
      title: "Praktek",
      target: "schedules"
    },
    {
      icon: "",
      title: "Login / Masuk",
      target: ""
    }
  ];
  title = "Vuetify.js";
  titleHover: boolean = false;

  linkTo(target: string) {
    this.$router.push({ name: target });
  }
}
</script>


<style scoped>
.pointer {
  cursor: pointer;
}
</style>
