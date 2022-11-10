<template>
    <div class="content-center">
        <div class="hexagon-item">
            <div class="hex-item">
                <div></div>
                <div></div>
                <div></div>
            </div>
            <div class="hex-item">
                <div></div>
                <div></div>
                <div></div>
            </div>
            <a class="hex-content">
                <span class="hex-content-inner">
                    <span class="icon">
                        <i class="fa fa-universal-access"></i>
                    </span>
                    <span class="title"><img @mouseover="mouseOver" @mouseout="mouseOut" class="maxwidth"
                            src="" /></span>
                </span>
                <svg viewBox="0 0 173.20508075688772 200" height="200" width="174" version="1.1"
                    xmlns="http://www.w3.org/2000/svg">
                    <path
                        d="M86.60254037844386 0L173.20508075688772 50L173.20508075688772 150L86.60254037844386 200L0 150L0 50Z"
                        fill="#0070AD"></path>
                </svg>
            </a>
        </div>
    </div>
</template>
<style>
.maxwidth {
    max-width: none;
    height: 130px;
    width: 130px;
}
</style>

<script>
export default {
    mounted() {
        var id = this.$el.id.replace('_page', '')
        this.$el.querySelector('.maxwidth').setAttribute("src", this.getImgUrl(id + '_off.png'));
    },
    methods: {
        mouseOver: function () {
            var id = this.$el.id.replace('_page', '')
            this.$el.querySelector('.maxwidth').setAttribute("src", this.getImgUrl(id + '.png'));
        },
        mouseOut: function () {
            var id = this.$el.id.replace('_page', '')
            this.$el.querySelector('.maxwidth').setAttribute("src", this.getImgUrl(id + '_off.png'));
        },
        getImgUrl: function (pic) {
            return require('../assets/img/icons/' + pic)
        }
    }
}
</script>