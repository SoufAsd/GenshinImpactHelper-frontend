<template>
  <div class="background-character">
    <div class="grid content-center">
      <div><img ref="image_character" :src="image" alt="" sizes="" srcset=""></div>
    </div>
    <Nuxt />
  </div>
</template>
<script>
import * as Vibrant from 'node-vibrant'
export default {
  props: {
    actualCharacter: []
  },
  data() {
    return {
      image : ""
    }
  },
  mounted() {
    // const colorThief = new ColorThief()
    //  document.querySelector('body').style.backgroundColor
    // Vibrant.from(this.actualCharacter.image).getPalette()
    //         .then((palette) => console.log(palette))
  },
  watch: {
    actualCharacter(oldVal, newVal) {
      this.getColors(this.actualCharacter.image);
      this.image = this.actualCharacter.image
      console.log(this.image)
    }
  },
  methods: {
    getColors(img) {
      Vibrant.from(img).maxColorCount(200).getPalette()
        .then((palette) => {
          var colorsP = []
          for (let color in palette) {
            var hex = palette[color].getHex()
            colorsP.push(hex)
          }
          this.name = colorsP
          document.querySelector('body').style.background = colorsP[colorsP.length-4]
        })
    }
  }
}
</script>