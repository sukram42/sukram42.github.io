<template>
    <v-main>
      <div class="main">
        <div class="left_part">
          <LeftBanner></LeftBanner>
        </div>
        <div class="right_part">

        </div>
      </div >
    </v-main>
</template>

<script lang="ts">
import Vue from "vue";
import LeftBanner from "@/components/leftbanner.component.vue";

export default Vue.extend({
  name: "App",

  components: {
    LeftBanner
  },

  data: () => ({
    //
  })
});
</script>
<style lang="scss">
  @import "variables";

  html, body {
    font-family: "Segoe UI Light", sans-serif;
  }

  .main {
    display: grid;
    height: 100vh;

    @media only screen and (max-width: $breakpoint) {
      grid-template-columns: 100%;
      grid-template-rows: 100%;
      grid-template-areas: "left";
    }
    @media only screen and (min-width: $breakpoint) {
      grid-template-columns: 40% 60%;
      grid-template-rows: auto;
      grid-template-areas: "left right";
    }
  }
  .left_part {
    grid-area: left;
    background-color: #444;
  }

  .right_part{
    grid-area: right;
  }

  .boldFont {
    font-family: "Segoe UI";
  }
</style>
