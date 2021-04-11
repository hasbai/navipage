<template>
  <v-app color="green">
    <v-main>
      <Home/>
    </v-main>
    <v-footer>
      <v-col class="text-center" cols="12">
        &copy; 2020-{{ new Date().getFullYear() }} All Rights Reserved
      </v-col>
    </v-footer>
  </v-app>
</template>

<script>
import Home from './views/Home.vue';

export default {
  name: 'App',

  components: {
    Home,
  },

  data: () => ({
    //
  }),
};
</script>

