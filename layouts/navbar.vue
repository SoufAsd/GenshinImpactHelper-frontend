<template>
  <div>
    <div class="nav flex justify-around flex-row">
      <div ref="left-nav" @mouseover="mouseOver" @mouseout="mouseOut" class="navbar-single-nav md:basis-1/3 right-hover">
        <a class="flex justify-center pt-8 sm:pt-0" target="_blank">
          <img class="single-nav" src="~/assets/img/icons/characters_off.png" />
        </a>
      </div>
      <div ref="middle-nav" @mouseover="mouseOver" @mouseout="mouseOut" class="navbar-single-nav md:basis-1/3">
        <a class="flex justify-center pt-8 sm:pt-0" target="_blank">
          <img class="single-nav" src="~/assets/img/icons/weapons_off.png" />
        </a>
      </div>
      <div ref="right-nav" @mouseover="mouseOver" @mouseout="mouseOut" class="navbar-single-nav md:basis-1/3 left-hover">
        <a class="flex justify-center pt-8 sm:pt-0" target="_blank">
          <img class="single-nav" src="~/assets/img/icons/items_off.png" />
        </a>
      </div>
    </div>
    <div class="take-me-home">

    </div>
    <Nuxt />
  </div>
</template>
<style>
.nav {
  transform: translate(0, 0);
  height: 124px;
  border-radius: 0 0 150px 150px;
  background-color: #f7f7f7;
}

.single-nav {
  height: 130px;
  width: 130px;
}

.take-me-home {
  display: none;
  margin: auto;
  height: 100px;
  width: 200px;
  border-radius: 0 0 150px 150px;
  background-color: #C0C0C0;
}

.navbar-single-nav:hover {
  background: linear-gradient(to bottom, #e8edec, #d2d1d3);
  box-shadow: 0px 3px 20px 0px black;
  transform: scale(1.2);
  color: black;
  cursor: pointer;
}

.left-hover:hover {
  border-radius: 0 0 150px 0;
}

.right-hover:hover {
  border-radius: 0 0 0 150px;
}
</style>
<script>
export default {
  methods: {
    mouseOver: function(e) {
      if(e.srcElement.querySelector('.single-nav') === null){
        var type = e.srcElement.src.split("icons/")[1].split("_off.png")[0]
        e.srcElement.setAttribute("src", this.getImgUrl(type + '.png'));
      }else{
        var type = e.srcElement.querySelector('.single-nav').src.split("icons/")[1].split("_off.png")[0]
        e.srcElement.querySelector('.single-nav').setAttribute("src", this.getImgUrl(type + '.png'));
      }
    },
    mouseOut: function(e) {
      if(e.srcElement.querySelector('.single-nav') === null){
        var type = e.srcElement.src.split("icons/")[1].split(".png")[0]
        e.srcElement.setAttribute("src", this.getImgUrl(type + '_off.png'));
      }else{
        var type = e.srcElement.querySelector('.single-nav').src.split("icons/")[1].split(".png")[0]
        e.srcElement.querySelector('.single-nav').setAttribute("src", this.getImgUrl(type + '_off.png'));
      }
    },
    getImgUrl: function (pic) {
      return require('../assets/img/icons/' + pic)
    }
  }
}
</script>