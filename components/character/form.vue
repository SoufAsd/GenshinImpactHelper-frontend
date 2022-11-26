<template>
  <div class="background-character">
    <div class="grid content-center">
      <div v-if="modaltype == ''" class="character-img"><img class="md:max-h-xl animate-pulse"
          style="max-height: 37rem;" ref="image_character" :src="image" alt="" sizes="" srcset=""></div>
          <div v-else class="p-10 w-full lg:max-w-full lg:flex">
            <ModalCharacter :modaltypekey="modaltype" :data-character="infos"></ModalCharacter>
          </div>
    </div>
  </div>
</template>
<script>
import * as Vibrant from 'node-vibrant'
export default {
  props: {
    actualCharacter: [],
    type: {
      type: String
    }
  },
  data() {
    return {
      image: "",
      infos: {},
      modaltype: "",
      color : ""
    }
  },
  updated() {
    this.modaltype = this.type
    this.infos['color'] = document.querySelector('#background').style.background
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
        "img": this.actualCharacter[0].image,
        "color" : this.color
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
          this.color = colorsP[colorsP.length - 4]
        })
    }
  }
}
</script>