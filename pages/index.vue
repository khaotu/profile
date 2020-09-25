<template>
  <div>
    <Toolbar/>
    <Bio 
    id="Bio"/>
    <Educations
    id="educations"
    style="min-height:100vh"/>
    <Experience 
    id="experience"
    style="min-height:80vh"/>
    <Contact 
    id="contact"
    style="min-height:25vh"
    title="CONTACT ME"
    :contacts="contacts"/>
    <Contact 
    style="min-height:40vh"
    title="FOLLOW ME"
    :contacts="social_media"/>
  </div>
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
  
}
</script>
