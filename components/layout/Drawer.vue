<template>
  <v-navigation-drawer>
    <v-toolbar flat dark color="blue darken-3">
      <v-list>
        <v-list-tile>
          <v-list-tile-title class="title">
            Globus HR
          </v-list-tile-title>
        </v-list-tile>
      </v-list>
    </v-toolbar>

    <v-divider></v-divider>

    <v-list dense class="pt-0">
      <v-list-tile
        v-for="item in links"
        :key="item.title"
        @click=""
      >
        <v-list-tile-action>
          <v-icon>{{ item.icon }}</v-icon>
        </v-list-tile-action>

        <v-list-tile-content>
          <v-list-tile-title>{{ item.text }}</v-list-tile-title>
        </v-list-tile-content>
      </v-list-tile>
    </v-list>
  </v-navigation-drawer>
</template>

<script>
// Utilities
import {
  mapMutations,
  mapState
} from 'vuex'

export default {
  name: 'drawer',
  data: () => ({
    logo: './img/vuetifylogo.png',
    links: [
      {
        to: '/',
        icon: 'home',
        text: 'Home'
      },
      {
        to: 'managing-director-owner',
        icon: 'mdi-account',
        text: 'Are you a MD or Owner?'
      },
      {
        to: '/360-degree-feedback-2',
        icon: 'mdi-clipboard-outline',
        text: '360 Degree Feedback'
      },
      {
        to: '/hr-system-for-sme-s',
        icon: 'mdi-format-font',
        text: 'HR System for SME\'s'
      },
      {
        to: '/leave-feedback',
        icon: 'mdi-chart-bubble',
        text: 'Feedback'
      },
      {
        to: '/about',
        icon: 'mdi-map-marker',
        text: 'About Us'
      },
      {
        to: '/contact-us',
        icon: 'mdi-bell',
        text: 'Contact Us'
      }
    ],
    responsive: false
  })
}
</script>

<style lang="scss">
  #app-drawer {
    .v-list__tile {
      border-radius: 4px;

      &--buy {
        margin-top: auto;
        margin-bottom: 17px;
      }
    }

    .v-image__image--contain {
      top: 9px;
      height: 60%;
    }

    .search-input {
      margin-bottom: 30px !important;
      padding-left: 15px;
      padding-right: 15px;
    }
  }
</style>
