<template>
  <div class="home">
    <div class="w-full h-full p-5">
      <p class="text-center">{{game.img}}</p>
    </div>
    <div @click="clicker" class="w-full h-full py-6 px-16 ">
      <p>{{game.txt}}</p><p @click="count = 5" v-if="count === 2">NO</p>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
//import HelloWorld from "@/components/HelloWorld.vue";

export default {
  name: "Home",
  components: {
  //  HelloWorld
},
data() {
  return {
    game : {
      img : 'MENU IMG',
      txt : 'START',
      music : ''
    },
    count : 0,
  }
},
methods: {
  clicker() {
    this.count ++
    this.refresh()
  },
  refresh() {
    if (this.count === 1) {
      this.game.img = 'ARCHIVES'
      this.game.txt = 'TEXT 1'
      this.game.music = 'feu'
    } else if (this.count === 2) {
      this.game.img = 'PORTE'
      this.game.txt = 'YES'
    } else if (this.count === 3) {
      this.game.img = 'NATURE'
      this.game.txt = 'TEXT 3'
      this.game.music = 'ost'
    } else if (this.count === 4) {
      this.game.img = 'FLEUR'
      this.game.txt = 'TEXT 3'
    } else if (this.count === 5) {
      this.game.img = 'MASQUE'
      this.game.txt = 'TEXT 3'
    } else if (this.count === 6) {
      this.game.img = 'METROPOLIS'
      this.game.txt = 'TEXT 3'
      this.game.music = 'violence'
    } else if (this.count === 7) {
      this.game.img = 'CONSERVE'
      this.game.txt = 'TEXT 3'
    } else {
      this.game.img = 'END'
      this.game.txt = 'END'
    }
  }
}
};
</script>
