<template>
  <b-container fluid>
    <b-row  align-h="center" class="mb-5" >
      <h1 style="color: #E76F51;">EXPERIENCES</h1>
    </b-row>
    <b-row  align-v="center" xs="12" md="6">
      <b-col class="mx-5 px-5">

        <div class="mb-5 mx-5 text-center experience"
        v-for="(i,n) in jobs"
        :key="n">
         <div class="line"/>
         <b-icon
         :id="`popover-button-${n}-open`"
         :icon="i.icon"
         :style="`width: 50px; height: 50px; margin-bottom: 55px; color: ${i.color};`">
         </b-icon>
         <b-popover
         style="margin-bottom:0px;"
         show
         :placement=" n%2 ===0 ? 'left': 'right'"
         :target="`popover-button-${n}-open`"
         >
           <!-- I start <strong>open</strong> -->
           <h4 style="color: #F4A261;">{{ i.company }}</h4>
           <h6 style="color: #E76F51;">{{ i.periods }}</h6>
           <h5 style="color: #264653;">{{ i.position }}</h5>
         </b-popover>
        </div>
      </b-col>
    </b-row>
  </b-container>
</template>

<script>
import simpleParallax from 'simple-parallax-js';
export default {
  data() {
    return {
      jobs: [
        {
          icon: 'star-fill',
          color: '#F4A261',
          periods: "02/2021 - Current",
          company: "THINKNET CO.,LTD.",
          position: "Web Developer"
        },
        {
          icon: 'briefcase-fill',
          color: '#2A9D8F',
          periods: "06/2019 - 01/2021",
          company: "GREENLINE SYNERGY CO.,LTD.",
          position: "Developer"
        },
        {
          icon: 'briefcase-fill',
          color: '#2A9D8F',
          periods: "06/2018 - 12/2018",
          company: "Agent One CO.,LTD.",
          position: "Intern Web Developer"
        }
      ]
    }
  },
  mounted() {
    const imageOdd = document.getElementsByClassName('experience-odd');
    new simpleParallax(imageOdd,{
      orientation: 'left',
      overflow: true,
      delay: 1
    });
    const imageEven = document.getElementsByClassName('experience-even');
    new simpleParallax(imageEven,{
      orientation: 'left',
      overflow: true,
      delay: 1
    });


  }
}
</script>

<style scoped>
  .line {
    width: 1px;
    height: 155px;
    background-color: gray;
    position: absolute;
    z-index: -1;
  }
  .experience {
    display: flex;
    justify-content: center;
  }
</style>
