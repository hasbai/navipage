<template>
<div>
  <!-- <canvas class="fireworks"></canvas> -->
  <v-img src="img/background.jpg" height="540">
    <div style="margin-top:200px;" class="text-center text-h4 white--text">{{quote}}</div>
  </v-img>
  
  <!-- <div style="margin-top:-180px;">{{quote}}</div> -->
  <v-card class="py-16 mb-16" :class="smAndUp ? 'px-8 mx-12' : 'px-4 mx-4'" elevation="8" style="margin-top:-80px;">
    <v-container fluid>
      <v-row justify="center" v-for="(type, index) in config.types" :key="index">
        <v-col cols="12" sm="10" md="6" lg="4"
          v-for="(site, index) in type.sites" :key="index">
          <v-hover v-slot="{ hover }">
            <v-card @click="open(site.link)" :elevation="hover ? 16 : 2">
              <div class="d-flex justify-start align-center py-4">
                <v-img :src="site.img" height="75" max-width="100" contain :class="smAndUp ? 'mx-8' : 'mx-4'"></v-img>
                <div>
                  <v-card-title class="headline" v-text="site.name"></v-card-title>
                  <v-card-subtitle v-text="site.description"></v-card-subtitle>
                </div>
              </div>
            </v-card>
          </v-hover>
        </v-col>
      </v-row>
    </v-container>
  </v-card>  
</div>
</template>

<script>
// import anime from 'animejs'
export default {
  name: 'Home',
  data(){
    return {
      config: {},
      quote: '',
    }
  },
  methods: {
    open(url){
      window.open(url)
    },
    getQuote(){
      this.$axios.get('https://v1.hitokoto.cn/?c=i')
      .then(res => {
          this.quote = res.data.hitokoto + '————《' + res.data.from + '》'
        })
      .catch(() => {
        console.log('not get')
      })
    }
  },
  computed: {
    smAndUp(){
      return this.$vuetify.breakpoint.smAndUp
    }
  },
  created(){
    this.$axios.get('config.json').then(
      res => {
        this.config = res.data
      }
    )
    // window.addEventListener('onload', this.getQuote)
    this.getQuote()
  },
  
}
</script>
<style scoped>
  .fireworks {
    /* position: absolute; */
    /* z-index:-2; */
  }
</style>