<template>
  <div class="about ">
    <!-- <div class="inline-block p-5" v-for="bug in bugs" :key="bug.id">
      <img v-bind:src="bug.icon_uri" alt="">
      <h1>[ {{bug.name['name-JPja']}} ]</h1>
      <h4>[ {{bug.name['name-EUfr']}} ]</h4>
      <input class="inline-block mr-3" type="checkbox" id="scales" name="scales"><p class="inline">{{bug.id}}</p>
    </div> -->
    <div class="inline-block " v-for="bug in bugs" :key="bug.id">
      <div class="inline-block text-center" v-if="
      bug.id === 3 || bug.id === 13 || bug.id === 14 || bug.id === 24 || bug.id === 30 || bug.id === 36 || bug.id === 50 || bug.id === 76 || bug.id === 77 || bug.id === 78 || bug.id === 42 || bug.id === 25
      " >
        <img v-bind:src="bug.icon_uri" alt="">
        <h1 >[ {{bug.name['name-JPja']}} ]</h1>
        <h4>[ {{bug.name['name-EUfr']}} ]</h4>
      </div>
    </div>


  </div>
</template>
<script>
    import axios from "axios";
    export default {
        mounted() {
            this.getData();
        },
        components: {

        },
        data() {
            return {
                bugs: {},
                bugsName: '',
            }
        },
        methods: {
            getData() {
                axios.get('http://acnhapi.com/v1/bugs')
                    .then((response) => {
                        this.bugs = response.data

                    })
                    .catch( (error) => {
                        console.log(error);
                    });

            },

        }
    }
</script>
