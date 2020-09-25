<template>
   <b-row 
      align-h="center" align-v="center" style="min-height:90vh">
        <b-col align-v="center" md="12" lg="6"> 
          <div class="profile">
            <b-img 
            class="girls"
            width= "400"
            height= "400"
            src="@/static/profile.PNG" 
            fluid alt="Responsive image"></b-img>
          </div>
        </b-col>
        <b-col align-h="center" align-v="center" class="box pa-3" md="12" lg="6">
          <div >
            <h1 class="pa-3">{{ name }}</h1>
            <h3>Here's who I am & what I do</h3>
            <p style="max-width:30em">
            I'm a developer at Greenline Synergy company. <br>
            One-year experience with Python HTML CSS and Javascript.
            I’m curious, and I enjoy work that challenges me to learn something new. 
            </p>
            <b-button
            class="px-5"
            variant="outline-primary"
            pill
            @click.prevent="downloadItem()">
              Resume
            </b-button>
          </div>
        </b-col>
      </b-row>
</template>

<script>
import anime from 'animejs/lib/anime.es.js';
import simpleParallax from 'simple-parallax-js';
export default {
  data() {
    return {
      name: "PEATAR RANGPRASERT",
      contacts: [
        {
          "media": "mail",
          "contact": "mailto:peatar.ra@gmail.com",
          "logo": "https://upload.wikimedia.org/wikipedia/commons/4/4e/Mail_%28iOS%29.svg"

        },
        {
          "media": "linkin",
          "contact": "https://www.linkedin.com/in/peatar-rangprasert-261aa01b4/",
          "logo": "https://www.iconfinder.com/data/icons/internet-2020/1080/LinkedinIcon-512.png"

        },
      ],
      social_media: [
        {
          "media": "facebook",
          "contact": "https://www.facebook.com/peetuu.kts",
          "logo": "https://www.iconfinder.com/data/icons/social-messaging-ui-color-shapes-2-free/128/social-facebook-2019-circle-512.png"

        },
        {
          "media": "twitter",
          "contact": "https://twitter.com/petu_97",
          "logo": "https://www.treasurers.org/ACTmedia/wp-content/uploads/2016/09/twitter-icon-360x360_0.png"
        },
         {
          "media": "ig",
          "contact": "https://www.instagram.com/kaoteta/",
          "logo": "https://tbrsteakhouse.com/wp-content/uploads/2018/11/instagram-colourful-icon.png"
        },
         {
          "media": "github",
          "contact": "https://github.com/khaotu",
          "logo": "https://cdn.iconscout.com/icon/free/png-256/github-153-675523.png"
        },
      ] 
    }
  },
  mounted() {
    anime({
      targets: '.profile',
      translateX: '18vw',
      duration: 5000
    });
    anime({
      targets: '.box',
      opacity: [0,1],
      duration: 10000,
      delay: 1000
    });
    var image = document.getElementsByClassName('girls');
    new simpleParallax(image,{
      scale: 1.2
    });
  },
  methods: {
    downloadItem () {
      window.open('https://drive.google.com/file/d/1O1ljiXPzqkKJe5Xd_okFsRvUqU6Y11C4/view?usp=sharing', '_blank');
      
    }
  }
  
}
</script>