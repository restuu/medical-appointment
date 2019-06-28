<template>
  <v-toolbar
    app
    :clipped-left="true"
  >
    <v-toolbar-side-icon
      v-if="drawer"
      @click.stop="onDrawerClick()"
      class="hidden-md-and-up"
    />
    <v-toolbar-title
      v-text="title"
      @mouseover="mouseOver()"
      @mouseout="mouseOver()"
      @click="cursor ? linkTo('home') : null"
      :class="{ [cursor]: titleHover }"
    />
    <v-spacer />
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
</template>

<script lang="ts">
import { Vue, Component, Model, Prop, Emit } from 'vue-property-decorator'

type NavItem = {
  icon: string;
  title: string;
  target?: string;
}

type NavTarget = {
  name: string;
}

@Component
class Toolbar extends Vue {
  titleHover: boolean = false;

  @Prop() drawer!: boolean;
  @Prop() items!: NavItem[];
  @Prop() title!: string;
  @Prop() cursor!: string | null;
  @Prop() linkToHome!: boolean;

  @Emit() onTitleOut() {
    this.titleHover = false;
  }
  @Emit() onDrawerClick() {
    return;
  }

  mouseOver() {
    this.titleHover = !this.titleHover;
  }

  linkTo(target: string) {
    this.$router.push({ name: target });
  }
}

export default Toolbar;
</script>
