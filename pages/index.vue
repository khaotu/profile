<template>
  <b-container fluid>
    <vue-scroll @handle-scroll="handleScroll">
    <div class="wave mb-5">
      <div class="avartar"/>
      <b-row class="justify-content-md-end" style="padding:30px">
        <Toolbar/>
      </b-row>
      <b-row style="margin-bottom:30px;">
        <b-col sm="12">
          <Bio
          id="Bio"/>
        </b-col>
      </b-row>
    </div>
    <b-row>
      <Educations
      id="educations"
      style="min-height:80vh"/>
    </b-row>
    <b-row>
      <Experience
      id="experience"
      style="min-height:80vh"/>
    </b-row>
    <b-row>
      <Contact
      id="contact"
      style="min-height:25vh"
      title="CONTACT ME"
      :contacts="contacts"/>
    </b-row>
    <b-row>
      <Contact
      style="min-height:40vh"
      title="FOLLOW ME"
      :contacts="social_media"/>
    </b-row>




    </vue-scroll>
  </b-container>
</template>

<script>
import Toolbar from '@/components/toolbar'
import Bio from '@/components/bio'
import Educations from '@/components/education'
import Contact from '@/components/contact'
import Experience from '@/components/experience'
export default {
  components: {
    Toolbar,
    Bio,
    Educations,
    Contact,
    Experience
  },
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
  methods: {
    handleScroll(vertical, horizontal, nativeEvent) {
              console.log(vertical, horizontal, nativeEvent)
          }
  }
}
</script>
<style scoped>
  .font {
    color: pink;
  }
  .avartar {
    width: 700px;
    height: 700px;
    background: url(../static/graduated.JPEG);
    /* opacity: 0.8; */
    background-size: cover;
    background-position: center;
    border-radius:0px 0px 50% 50%;
    position: absolute;
    margin-top: -130px;
    margin-left: -100px;
  }
  .wave {
    position: relative;
    background: linear-gradient(-45deg, #ffff, #ee7752, #e73c7e, #23a6d5, #23d5ab);
  	background-size: 400% 400%;
    height: 140vh;
  	animation: gradient 15s ease infinite;
  }
  .wave:before {
    content: '';
    position: absolute;
    bottom: 0;
    left: 0;
    width: 100%;
    height: 220px;
    background: url(../static/wave.png);
    background-size: cover;
    background-repeat: no-repeat;
  }

@keyframes gradient {
	0% {
		background-position: 0% 50%;
	}
	50% {
		background-position: 100% 50%;
	}
	100% {
		background-position: 0% 50%;
	}
}
</style>
