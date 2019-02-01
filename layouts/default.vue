<template>
  <v-app light>
    <v-navigation-drawer
      fixed
      clipped
      v-model="drawer"
      app
    >
      <v-list dense>
        <v-list-tile v-for="item in items" :key="item.text" @click="">
          <v-list-tile-action>
            <v-icon>{{ item.icon }}</v-icon>
          </v-list-tile-action>
          <v-list-tile-content>
            <v-list-tile-title>
              {{ item.text }}
            </v-list-tile-title>
          </v-list-tile-content>
        </v-list-tile>
      </v-list>
    </v-navigation-drawer>
    <toolbar/>
    <v-content>
      <v-container fill-height>
        <v-layout justify-center align-center>
          <v-flex shrink>
            <v-tooltip right>
              <v-btn
                icon
                large
                :href="source"
                target="_blank"
                slot="activator"
              >
                <v-icon large>code</v-icon>
              </v-btn>
              <span>Source</span>
            </v-tooltip>
          </v-flex>
        </v-layout>
      </v-container>
    </v-content>
  </v-app>
</template>

<script>
import Drawer from "../components/layout/Drawer";
import Toolbar from "../components/layout/Toolbar";
export default {
  components: {Toolbar, Drawer},
  data() {
    return {
      drawer: true,
      items: [
        {
          to: '/',
          icon: 'home',
          text: 'Home'
        },
        {
          to: 'managing-director-owner',
          icon: 'person',
          text: 'Are you a MD or Owner?'
        },
        {
          to: '/360-degree-feedback-2',
          icon: '360',
          text: '360 Degree Feedback'
        },
        {
          to: '/hr-system-for-sme-s',
          icon: 'people',
          text: 'HR System for SME\'s'
        },
        {
          to: '/leave-feedback',
          icon: 'feedback',
          text: 'Feedback'
        },
        {
          to: '/about',
          icon: 'help',
          text: 'About Us'
        },
        {
          to: '/contact-us',
          icon: 'contact_phone',
          text: 'Contact Us'
        },
        {
          to: '/news-and-events',
          icon: 'event',
          text: 'News & Events'
        }
      ]
    }
  }
}
</script>
