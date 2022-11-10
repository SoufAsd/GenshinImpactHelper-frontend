<template>
  <div class="background-character">
    <div class="grid content-center">
      <div class="character-img"><img class="md:max-h-xl animate-pulse" style="max-height: 37rem;" ref="image_character"
          :src="image" alt="" sizes="" srcset=""></div>
      <ModalCharacter :modaltype="this.modaltype"></ModalCharacter>
    </div>
    <Nuxt />
  </div>
</template>
<script>
import * as Vibrant from 'node-vibrant'
export default {
  props: {
    actualCharacter: [],
  },
  data() {
    return {
      image: "",
      infos: {},
      modaltype : "",
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
      this.getColors(this.actualCharacter[0].image);
      this.image = this.actualCharacter[0].image
      this.infos = { 
        "description": this.actualCharacter[0].description,
        "name": this.actualCharacter[0].name,
        "nation": this.actualCharacter[0].nation,
        "birthday": this.actualCharacter[0].birthday,
        "title": this.actualCharacter[0].title,
        "vision": this.actualCharacter[0].vision,
      }
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
          document.querySelector('#background').style.background = colorsP[colorsP.length - 4]
        })
    }
  }
}
</script>