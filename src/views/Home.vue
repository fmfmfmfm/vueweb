<template>
  <v-content>
    <v-container grid-list-lg fluid>
     <v-layout row wrap>
    <v-flex xs12 sm12 fluid md12 lg11>
      <v-card>
        <div class="coon">
        	<h2 class="conheght">电影</h2>
        	<v-btn small round class="more">更多</v-btn>
        </div>
        <v-divider />
        <v-container fluid  >
          <v-layout row wrap >
            <v-flex v-for="i in 12" :key="i" sm4 xs6 md3 lg2>
            	<v-card flat tile>
                <v-card-media
                  :src="`https://randomuser.me/api/portraits/men/${i + 20}.jpg`"
                  height="285px"
                ></v-card-media>
              </v-card>
              
            </v-flex>
          </v-layout>
        </v-container>
        <div class="coon">
        	<h2 class="conheght">电影</h2>
        	<v-btn small round class="more">更多</v-btn>
        </div>
        <v-divider />
        <v-container fluid grid-list-sm>
          <v-layout row wrap>
            <v-flex v-for="i in 12" :key="i" sm4 xs6 md3 lg2>
              <v-card flat tile>
                <v-card-media
                  :src="`https://randomuser.me/api/portraits/women/${i + 5}.jpg`"
                  height="285px"
                ></v-card-media>
              </v-card>
            </v-flex>
          </v-layout>
        </v-container>
        <v-footer class="mt-5"></v-footer>
      </v-card>
    </v-flex>
  </v-layout>
   </v-container>
    </v-content>
</template>

<script>
// @ is an alias to /src
import HelloWorld from '@/components/HelloWorld.vue'

export default {
  name: 'home',
  components: {
    HelloWorld
  }
}
</script>
<style type="text/css">
	.more{
		height: 25px;
		line-height: 25px;
		float: right;
	}
	.conheght{
		margin-left: 22px;
		float: left;
		display:block;
	}
	.coon{
		height: 45px;
		line-height: 45px;
	}
</style>
