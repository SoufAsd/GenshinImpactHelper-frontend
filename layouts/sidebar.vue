<template>
    <div ref="colordetector" class="color-detector">
        <nav class="absolute animation-fadein left-5 top-5 h-16 w-16">
            <a @click="$router.back()">
                <div class="back-home rounded-full bg-sky-500/50">back</div>
            </a>
        </nav>
        <nav class="sidebar animation-fadein rounded-lg inset-y-0 left-3 drop-shadow-md">
            <div class="content flex flex-col">
                <div @click="openmodel" class="switcher rounded-lg drop-shadow-lg from-center" data-value="Infos">
                    <img height="45px" width="45px" src="~/assets/img/svgs/infos.svg" />
                </div>
                <div @click="openmodel" class="switcher rounded-lg drop-shadow-lg" data-value="Ascension">
                    <img height="40px" width="40px" src="~/assets/img/svgs/up.svg" />
                </div>
                <div @click="openmodel" class="switcher rounded-lg drop-shadow-lg" data-value="Talents"><img
                        height="40px" width="40px" src="~/assets/img/svgs/star.svg" /></div>
                <div @click="openmodel" class="switcher rounded-lg drop-shadow-lg" data-value="Passive"><img
                        height="40px" width="40px" src="~/assets/img/svgs/chain.svg" /></div>
            </div>
        </nav>
        <nav class="sidebar animation-fadein rounded-lg inset-y-0 right-3 drop-shadow-md">
            <div class="content flex flex-col">
                <div @click="openmodel" class="switcher rounded-lg drop-shadow-lg" data-value="Constellation"><img
                        height="40px" width="40px" src="~/assets/img/svgs/const.svg" /></div>
                <div @click="openmodel" class="switcher rounded-lg drop-shadow-lg" data-value="Teams"><img height="40px"
                        width="40px" src="~/assets/img/svgs/team.svg" /></div>
                <div @click="openmodel" class="switcher rounded-lg drop-shadow-lg" data-value="Weapons"><img
                        height="40px" width="40px" src="~/assets/img/svgs/weapon.svg" /></div>
                <div @click="openmodel" class="switcher rounded-lg drop-shadow-lg" data-value="Soon">!</div>
            </div>
        </nav>
        <Nuxt :nuxt-child-key="modaltype" />
    </div>
</template>
<script>
import Vue from 'vue'

export default {
    data: function() {
        return{
            modaltype : ""
        }
    },
    mounted() {

    },
    methods: {
        openmodel: function (e) {
            // var modal = document.querySelector("#modal-container")
            this.modaltype = e.target.getAttribute("data-value")
            // document.querySelector("#modal-container").setAttribute("data-value",this.modaltype)
            if (document.querySelector(".active")) {
                document.querySelector(".active").classList.remove("active")
                e.target.classList.add("active")
                // if (modal.classList.contains("out")) {
                //     modal.classList.remove("out")
                //     modal.classList.add("open")
                // } else {
                //     modal.classList.add("out")
                //     setTimeout(function () {
                //         modal.classList.remove("out")
                //     }, 500);
                // }
            } else {
                e.target.classList.add("active")
                document.querySelector(".character-img").classList.add("fadeout-img")
                // modal.classList.add("open")
            }
        },
    }
}
</script>