<template>
  <b-container >
    <b-row  align-h="center" class="mb-5">
      <h1>EDUCATION</h1>
    </b-row>
    <b-row  align-v="center">
      <b-col>
        <b-img 
        class="graduated"
        width= "400"
        height= "400"
        src="@/static/graduated.JPEG" 
        fluid alt="Responsive image">
        </b-img>
      </b-col>
      <b-col>
        <div class="mb-5">
          <h2>2015 - 2019</h2>
          <h3>King Mongkut's Institute of Technology Ladkrabang</h3>
          <h4>Bachelor of Computer Science</h4>
        </div>
        <div>
          <h3>2012 - 2015</h3>
          <h4>Prachinratsadornamroong School</h4>
          <h5>Senior High School</h5>
        </div>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import simpleParallax from 'simple-parallax-js';
export default {
  mounted() {
    const image = document.getElementsByClassName('graduated');
    new simpleParallax(image,{
      orientation: 'right',
      scale: 1.2,
      overflow: true
    });

  }
}
</script>