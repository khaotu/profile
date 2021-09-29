<template>
    <div>
        <v-btn color="success"
        @click="transformImageUrlToFile('https://nextbest-store.s3-ap-southeast-1.amazonaws.com/campaign/1632844627608.png')">text</v-btn>
    </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: ''
    },
    uri: {
      type: String,
      default: ''
    },
    imageUrl: {
      type: String,
      default: 'https://nextbest-store.s3-ap-southeast-1.amazonaws.com/campaign/1632844627608.png'
    }
  },
  data() {
    return {
      image: null,
      tempImage: null,
      imageLoading: false,
      uploading: false,
      requireFields: {
        title: [(value) => !!value || 'Title is required.'],
        uri: [
          (value) => !!value || 'URI is required.',
          (value) =>
            (value && value.split(' ').length < 2) || 'URI is not allow space.',
          (value) =>
            new RegExp('^https://', 'i').test(value) || 'https is required.'
        ]
      },
      imageRules: [
        (value) => !!value || 'Image is required.',
        (value) =>
          !value || value.size < 1000000 || 'Size should be less than 1 MB!'
      ]
    }
  },
  computed: {
    renderTitle: {
      get() {
        return this.title
      },
      set(value) {
        this.$emit('setNewTitle', value)
      }
    },
    renderUri: {
      get() {
        return this.uri
      },
      set(value) {
        this.$emit('setNewUri', value)
      }
    }
  },
  async mounted() {
    try {
      const result = await this.$axios.get(this.imageUrl)
      console.log(result)
      this.image = this.imageUrl
        ? await this.transformImageUrlToFile(this.imageUrl)
        : null
    console.log(this.image)
    } catch (e) {
      console.log(e)
    }
  },
  methods: {
    async transformImageUrlToFile(imageUrl) {
      const fileName = imageUrl.split('/').pop()
      const baseFile = await this.getBase64FromUrl(imageUrl)
      return this.base64toFile(baseFile, fileName)
    },
    getImageSize(file) {
      return new Promise((cb, cbErr) => {
        try {
          var reader = new FileReader()
          reader.readAsDataURL(file)
          reader.onload = function (e) {
            var image = new Image()

            image.src = e.target.result
            image.onload = function () {
              var height = this.height
              var width = this.width

              cb({ height, width })
            }
          }
        } catch (e) {
          cbErr(e)
        }
      })
    },
    getImageAspectRatio(w, h) {
      function gcd(a, b) {
        return b == 0 ? a : gcd(b, a % b)
      }

      const r = gcd(w, h)
      return `${w / r}:${h / r}`
    },
    async getBase64FromUrl(url) {
      const data = await fetch(url)
      const blob = await data.blob()
      return new Promise((resolve) => {
        const reader = new FileReader()
        reader.readAsDataURL(blob)
        reader.onloadend = () => {
          const base64data = reader.result
          resolve(base64data)
        }
      })
    },
    base64toFile(dataurl, filename) {
      var arr = dataurl.split(','),
        mime = arr[0].match(/:(.*?);/)[1],
        bstr = atob(arr[1]),
        n = bstr.length,
        u8arr = new Uint8Array(n)

      while (n--) {
        u8arr[n] = bstr.charCodeAt(n)
      }

      return new File([u8arr], filename, { type: mime })
    }
  }
}
</script>
