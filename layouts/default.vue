<template>
  <div id="app" class="container bv-example-row bv-example-row-flex-cols">
    <b-container fluid style="padding:0; margin:0">
      <!-- <b-row class="justify-content-md-end">
          <Toolbar/>
      </b-row> -->
      <b-row class="justify-content-md-center">
          <nuxt />
      </b-row>
    </b-container>


  </div>
</template>

<style>
</style>

<script>

import Toolbar from '@/components/toolbar'
export default {
  components: {
    Toolbar
  },
}
</script>
<style>
  .container {
    width: 100vw;
    max-width: 100%;
    overflow-x: hidden;
  }
</style>
