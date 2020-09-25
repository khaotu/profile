<template>
  <b-container fluid>
    <b-row  align-h="center" class="mb-3" >
      <h1>WORK EXPERIENCES</h1>
    </b-row>
    <b-row  align-v="center" xs="12" md="6">
      <b-col class="mx-5 px-5">
        <div class="mb-5 mx-5">
          <h2>06/2019 - Current</h2>
          <h3>GREENLINE SYNERGY CO.,LTD.</h3>
          <h4>Developer</h4>
        </div>

        <div class="mb-5 mx-5">
          <h3>06/2018 - 12/2018</h3>
          <h4>Agent One CO.,LTD.</h4>
          <h5>Intern Web Developer</h5>
        </div>
      </b-col>
      <b-col>
        <b-img 
        class="experience"
        width= "500"
        src="@/static/girl.png" 
        fluid alt="Responsive image">
        </b-img>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import simpleParallax from 'simple-parallax-js';
export default {
  mounted() {
    const image = document.getElementsByClassName('experience');
    new simpleParallax(image,{
      orientation: 'left',
      overflow: true
    });

  }
}
</script>