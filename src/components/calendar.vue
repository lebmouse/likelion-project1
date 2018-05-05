<template>
  <v-container fluid grid-list-xl class="black">
    <v-slide-x-transition mode="out-in">
      <v-layout row wrap align-center>

        <v-flex xs1>
          <v-btn color="grey darken-4" fab dark v-on:click="lefting">
            <v-icon>keyboard_arrow_left</v-icon>
          </v-btn>
        </v-flex>

        <v-flex xs10>
          <div id="calendar">
            <table>
              <tr>
                <th v-for="m in month" :key="m">{{m}}</th>
              </tr>
              <tr v-for="i in 31" :key="i">
                <td v-for="j in 12" :key="j" v-on:click="recording">
                  {{j}},{{i}}
                  <v-btn color="black">text</v-btn>
                </td>
              </tr>
            </table>
          </div>
        </v-flex>

        <v-flex xs1>
          <v-btn color="grey darken-4" fab dark v-on:click="righting">
            <v-icon>keyboard_arrow_right</v-icon>
          </v-btn>
        </v-flex>

      </v-layout>
    </v-slide-x-transition>
  </v-container>

</template>

<script>
  export default {
    data() {
      return {
        month: ['January', 'Febuary', 'March', 'April', 'May', 'June', 'July', 'August', 'September', 'October',
          'November', 'December'
        ],
        nbsp: '&nbsp;'
      }
    },
    methods: {
      calendarWidth() {
        console.log(document.getElementById('calendar').clientWidth);
        return document.getElementById('calendar').clientWidth / 3
      },
      lefting() {
        console.log(this.calendarWidth())
        document.getElementById('calendar').scrollLeft -= this.calendarWidth();
      },
      righting() {
        // console.log(this.calendarWidth())
        document.getElementById('calendar').scrollLeft += this.calendarWidth();
      },
      recording() {

      }
    }
  }

</script>

<style scoped>
  #calendar {
    box-sizing: border-box;
    width: 100%;
    /* height:100%; */
    /* margin-top: -12px; */
    /* margin-bottom: -8px; */
    padding: 0;
    overflow-x: scroll;
    scroll-behavior: smooth;
  }

  ::-webkit-scrollbar {
    width: 15px;
  }

  /* this targets the default scrollbar (compulsory) */

  ::-webkit-scrollbar-track {
    background-color: red;
    border-bottom-left-radius: 5px;
    border-bottom-right-radius: 5px;
    width: 2500px;
  }

  /* the new scrollbar will have a flat appearance with the set background color */

  ::-webkit-scrollbar-thumb {
    background-color: #212121;
    border-bottom-left-radius: 5px;
    border-bottom-right-radius: 5px;
    /* width: 800px; */
  }

  /* this will style the thumb, ignoring the track */

  ::-webkit-scrollbar-button:no-button {
    /* background-color:blue;
    border-radius: 5px;
    width:50px; */
  }

  /* optionally, you can style the top and the bottom buttons (left and right for horizontal bars) */

  table {
    width: 2400px;
    /* min-width: 1000px; */
    /* height:10%; */
    border-collapse: collapse;
    border: 1px solid white;
    margin: 0;
    padding: 0;
  }

  th {
    border: 1px solid white;
    background: linear-gradient(#E0E0E0, #FAFAFA, #E0E0E0);
    width: 100px;
    color: black;
    font-size: 12px;
  }

  td {
    border: 1px solid white;
    color: white;
    transition: 1s linear;
  }

  td:hover {
    background-color: #616161;
    transition: 0.5s ease;
  }

</style>
