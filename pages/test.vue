<template >
  <b-container style="overflow: hidden;" >
    <b-row >

      <b-button @click="view=0" variant="primary">
          box 1
      </b-button>
      <b-button @click="view=20" variant="primary">
          box 2
      </b-button>
      <b-button @click="view=40" variant="primary">
          box 3
      </b-button>
      <b-button @click="view=60" variant="primary">
          box 4
      </b-button>
      <b-button @click="view=80" variant="primary">
          box 5
      </b-button>
      <!-- <b-navbar toggleable="lg" type="" variant="transparent">
          <b-navbar-brand href="#" class="font">About me</b-navbar-brand>
          <b-navbar-brand href="#educations" class="font">Educations</b-navbar-brand>
          <b-navbar-brand href="#experience" class="font">Work Experience</b-navbar-brand>
          <b-navbar-brand href="#contact" class="font">Contact</b-navbar-brand>
      </b-navbar> -->
    </b-row>
    <b-row :style="`transform: translateY(-${view}%);  transition:1s`"
  >
  {{ view }}
      <div class="box" style="background-color:blue;"/>
      <div class="box" style="background-color:pink;"/>
      <div class="box" style="background-color:green;"/>
      <div class="box" style="background-color:aqua;"/>
      <div class="box" style="background-color:yellow;"/>
    </b-row>
  </b-container>

</template>

<script>
import Toolbar from '@/components/toolbar'
import Bio from '@/components/bio'
import Educations from '@/components/education'
import Contact from '@/components/contact'
import Experience from '@/components/experience'

export default{
    components: {
      Toolbar,
      Bio,
      Educations,
      Contact,
      Experience
    },
    data() {
      return {
        view: 0
      }
    }
  }
</script>

<style scoped>
 .box {
   width: 100vw;
   height: 100vh;


 }
</style>
