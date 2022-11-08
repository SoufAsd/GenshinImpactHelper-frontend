<template>
    <div ref="color-detector" class="color-detector">
        <nav class="absolute animation-fadein left-5 top-5 h-16 w-16">
            <a @click="$router.back()"><div class="back-home rounded-full bg-sky-500/50">back</div></a>
        </nav>
        <nav class="sidebar animation-fadein rounded-lg inset-y-0 left-3 drop-shadow-md">
            <div class="content flex flex-col">
                <div class="switcher drop-shadow-lg from-center" data-value="Infos">
                    <img  height="45px" width="45px" src="~/assets/img/svgs/infos.svg" />
                </div>
                <div class="switcher drop-shadow-lg" data-value="Ascension">
                    <img height="40px" width="40px" src="~/assets/img/svgs/up.svg" />
                </div>
                <div class="switcher drop-shadow-lg" data-value="Talents"><img  height="40px" width="40px" src="~/assets/img/svgs/star.svg" /></div>
                <div class="switcher drop-shadow-lg" data-value="Passive"><img height="40px" width="40px" src="~/assets/img/svgs/chain.svg" /></div>
            </div>
        </nav>
        <nav class="sidebar animation-fadein rounded-lg inset-y-0 right-3 drop-shadow-md">
            <div class="content flex flex-col">
                <div class="switcher drop-shadow-lg" data-value="Constellations"><img height="40px" width="40px" src="~/assets/img/svgs/const.svg" /></div>
                <div class="switcher drop-shadow-lg" data-value="Teams"><img height="40px" width="40px" src="~/assets/img/svgs/team.svg" /></div>
                <div class="switcher drop-shadow-lg" data-value="Weapons"><img height="40px" width="40px" src="~/assets/img/svgs/weapon.svg" /></div>
                <div class="switcher drop-shadow-lg" data-value="Soon">!</div>
            </div>
        </nav>
        <Nuxt />
    </div>
</template>
<script>
import Vue from 'vue'

export default Vue.extend({
    mounted() {

    },
})
</script>