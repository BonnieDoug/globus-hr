<template>
  <v-toolbar
    color="white"
    dark
    fixed
    clipped-left
    height="70"
    app
  >
    <!--<v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>-->
    <!--<v-icon class="mx-3">fa-youtube</v-icon>-->
    <!--<v-icon class="mx-3">fa-youtube</v-icon>-->
    <v-spacer></v-spacer>

    <v-toolbar-title class="mr-5 align-center">
      <img height="55" src="logo.png" class="mt-1">
    </v-toolbar-title>
    <v-spacer></v-spacer>
  </v-toolbar>
</template>

<script>

  import {
    mapMutations
  } from 'vuex'

  export default {
    name: 'toolbar',
    data: () => ({
      notifications: [
        'Mike, John responded to your email',
        'You have 5 new tasks',
        'You\'re now a friend with Andrew',
        'Another Notification',
        'Another One'
      ],
      title: 'Globus HR',
      responsive: false,
      responsiveInput: false
    }),

    watch: {
      '$route'(val) {
        this.title = val.name
      }
    },

    mounted() {
      this.onResponsiveInverted()
      window.addEventListener('resize', this.onResponsiveInverted)
    },
    beforeDestroy() {
      window.removeEventListener('resize', this.onResponsiveInverted)
    },

    methods: {
      ...mapMutations('app', ['setDrawer', 'toggleDrawer']),
      onClickBtn() {
        this.setDrawer(!this.$store.state.app.drawer)
      },
      onClick() {
        //
      },
      onResponsiveInverted() {
        if (window.innerWidth < 991) {
          this.responsive = true
          this.responsiveInput = false
        } else {
          this.responsive = false
          this.responsiveInput = true
        }
      }
    }
  }
</script>

<style>
  #core-toolbar a {
    text-decoration: none;
  }
</style>
