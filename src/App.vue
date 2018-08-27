<template>
  <v-app id="inspire">
    <v-navigation-drawer
      v-model="drawer"
      fixed
      clipped
      class="grey lighten-4"
      app
    >
      <v-list
        dense
        class="grey lighten-4"
      >
        <template v-for="(item, i) in items">
          <v-layout
            v-if="item.heading"
            :key="i"
            row
            align-center
          >
            <v-flex xs6>
              <v-subheader v-if="item.heading">
                {{ item.heading }}
              </v-subheader>
            </v-flex>
          </v-layout>
          <v-divider
            v-else-if="item.divider"
            :key="i"
            dark
            class="my-3"
          ></v-divider>
          <v-list-tile
            v-else
            :key="i"
            @click=""
          >
            <v-list-tile-action>
              <v-icon>{{ item.icon }}</v-icon>
            </v-list-tile-action>
            <v-list-tile-content>
              <v-list-tile-title class="grey--text">
                {{ item.text }}
              </v-list-tile-title>
            </v-list-tile-content>
          </v-list-tile>
        </template>
      </v-list>
    </v-navigation-drawer>
    <v-toolbar color="amber" app absolute clipped-left fixed >
      <v-toolbar-side-icon   @click.native="drawer = !drawer" v-resize="onResize"></v-toolbar-side-icon>
      <span class="title ml-3 mr-5">Google&nbsp;<span class="text">Keep</span></span>
      <v-text-field
        solo-inverted
        flat
        hide-details
        label="Search"
        prepend-inner-icon="search"
      ></v-text-field>
      <v-spacer></v-spacer>
    </v-toolbar>
    <router-view />
    </v-parallax>
  </v-app>
</template>

<script>
  export default {
    data(){
      return{
      drawer: null,
      items: [
        { icon: 'lightbulb_outline', text: '首页' },
        { icon: 'touch_app', text: '最热影片' },
        { divider: true },
        { heading: '电影' },
        { icon: 'archive', text: 'Archive' },
        { icon: 'delete', text: 'Trash' },
        { divider: true }
      ],
      x:0
    }
  },
    props: {
      source: String
    },
    methods:{
      // onScroll(e){
      //   this.offsetTop = window.pageYOffset || document.documentElement.scrollTop
      //   if (this.offsetTop>0) {
      //     console.log(this.offsetTop)
      //   }
      // }
      onResize(){
        this.x = {x:window.innerWidth}
        if (this.x.x<960) {
          @click.native="drawer = drawer"
        }
      },
      mounted(){
        this.onResize()
      }
    }
  }
</script>

<style>
  #keep main .container {
    height: 660px;
  }
  .v-navigation-drawer__border {
    display: none;
  }
  .text {
    font-weight: 400;
  }
  #inspire{
    position: relative;
  }
</style>