<template>
  <div>
    <div class="index">
      <logo />
      <div class="flex justify-center">
        <NuxtLink to="/character">
          <navigator id="characters_page" ref="characters" />
        </NuxtLink>
        <navigator id="weapons_page" ref="weapons" />
        <navigator id="items_page" ref="items" />
      </div>
    </div>
    <div>
      <backgroundCloud />
    </div>
  </div>
</template>

<script lang="ts">
import Vue from 'vue'

export default Vue.extend({
  name: 'IndexPage',
  mounted() {
    this.onWindowLoad()
  },
  methods: {
    onWindowLoad: function() {
      var refs = this.$refs;
      Object.keys(refs).forEach((el) => {
        (refs[el] as Vue).$el.querySelector('.maxwidth')!.setAttribute("src", this.getImgUrl(el+'_off.png'))
      });
    },
    getImgUrl : function(pic : string) {
      return require('../assets/img/icons/'+pic)
  }
  },
})

</script>
