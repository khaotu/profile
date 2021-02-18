<template>
  <b-container >
    <b-row  align-h="center" class="mb-5 mt-5">
      <h1 style="color: #E76F51;">EDUCATION</h1>
    </b-row>
    <b-row  align-v="center" class="justify-content-md-around">
      <!-- <b-col>
        <b-img
        class="graduated"
        width= "400"
        height= "400"
        src="@/static/graduated.JPEG"
        fluid alt="Responsive image">
        </b-img>
      </b-col> -->
      <b-col v-for="(i,n) in educations"
      :key="n"
      sm="12" md="12" lg="4"
      >
      <b-card
       border-variant="info"
       :header="i.periods"
       header-border-variant="primary"
       header-bg-variant="white"
       header-text-variant="primary"
       align="center"
       class="card-bg"
     >
       <b-card-text style="padding:30px 0;">
         <h3 style="color: white;">{{ i.place }}</h3>
         <h4 style="color: white;">{{ i.degree }}</h4>
       </b-card-text>
     </b-card>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import anime from 'animejs/lib/anime.es.js';
import simpleParallax from 'simple-parallax-js';
export default {
  mounted() {
    const image = document.getElementsByClassName('edu-box');
    new simpleParallax(image,{
      orientation: 'up',
      scale: 1.5,
      overflow: true
    });
  },
  data() {
    return {
      educations: [
        {
          periods: "2015 - 2019",
          place: "King Mongkut's Institute of Technology Ladkrabang",
          degree: "Bachelor of Computer Science"
        },
        {
          periods: "2012 - 2015",
          place: "Prachinratsadornamroong School",
          degree: "Senior High School"
        }
      ]
    }
  }
}
</script>

<style media="screen">
  .card-bg {
      background: linear-gradient(-45deg,  #23a6d5, #23d5ab);
      display: flex;
      justify-content: center;
      min-height: 350px;
  }
</style>
