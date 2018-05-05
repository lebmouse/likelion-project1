<template>
  <div id="app">
    <v-app dark>
      <v-navigation-drawer fixed clipped v-model="drawer" app temporary width="200" class="grey darken-4">
        <v-list>
          <v-list-tile value="true" v-for="(item, i) in items" :key="i">
            <v-list-tile-action>
              <v-icon v-html="item.icon"></v-icon>
            </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title v-text="item.title"></v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </v-list>
      </v-navigation-drawer>

      <v-toolbar fixed app clipped-left height="40" class="transparent">
        <v-toolbar-side-icon @click.stop="drawer = !drawer"></v-toolbar-side-icon>
        <v-toolbar-title v-text="title"></v-toolbar-title>
        <v-spacer></v-spacer>
      </v-toolbar>

      <v-content>
        <!-- <v-container fluid class="black scroll-x" id="scroll-target" grid-list-xl>
          <v-slide-y-transition mode="out-in">
            <v-layout row wrap align-center justify-center>
              <v-flex xs1>
                <v-btn color="grey darken-4" fab dark>
                  <v-icon>keyboard_arrow_left</v-icon>
                </v-btn>
              </v-flex>
              <v-flex xs10>
                <calendar></calendar>
              </v-flex>
              <v-flex xs1>
                <v-btn color="grey darken-4" fab dark>
                  <v-icon>keyboard_arrow_right</v-icon>
                </v-btn>
              </v-flex>
            </v-layout>
          </v-slide-y-transition>
        </v-container> -->
        <calendar></calendar>

      </v-content>
      <!-- <v-footer app>
        <span>&copy; 2018</span>
      </v-footer> -->
    </v-app>
  </div>
</template>

<script>
  import leftBar from './components/left-bar.vue'
  import calendar from './components/calendar.vue'
  export default {
    name: 'App',
    data() {
      return {
        drawer: true,
        items: [{
          icon: 'bubble_chart',
          title: 'Inspire'
        }],
        title: 'RECORDING'
      }
    },
    components: {
      'left-bar': leftBar,
      'calendar': calendar
    },
  }

</script>

<style scoped>


</style>
