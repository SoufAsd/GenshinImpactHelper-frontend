<template>
  <div>
    <logo />
    <NuxtLink to="/character">
      <div class="">
        <navigator id="character_page" ref="character"/>
        <navigator id="weapons_page" ref="weapons"/>
      </div>
    </NuxtLink>
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
        onWindowLoad() {
            console.log(this.$refs);
        },
    },
})

</script>
