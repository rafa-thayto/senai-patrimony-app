<template>
  <div>

    <!-- <v-container>
    </v-container> -->
    <!-- <v-card flat> -->
      <Header :title="title"/>
      <!-- <v-layout row pb-2> -->
        <!-- <v-flex xs8 offset-xs2>
          <v-card class="card--flex-toolbar">
            <v-toolbar card prominent>
              <v-toolbar-title class="body-2 grey--text">Title</v-toolbar-title>
              <v-spacer></v-spacer>
              <v-btn icon>
                <v-icon>search</v-icon>
              </v-btn>
              <v-btn icon>
                <v-icon>apps</v-icon>
              </v-btn>
              <v-btn icon>
                <v-icon>more_vert</v-icon>
              </v-btn>
            </v-toolbar>
            <v-divider></v-divider>
            <v-card-text style="height: calc(100%);">
              <Login />
            </v-card-text>

          </v-card>
        </v-flex> -->
      <!-- </v-layout> -->
    <!-- </v-card> -->
      <v-layout row>
        <v-flex sm8 class="d-none">
          colocar imagem
        </v-flex>
        <v-flex xs12 sm4>
          <v-card dark color="deep-purple darken-1">
            <v-container class="pl-5 pr-5">
              <Login />
            </v-container>
          </v-card>
        </v-flex>
      </v-layout>
  </div>
</template>

<script>
// @ is an alias to /src
import Login from '@/components/Login.vue'
import Header from '@/components/Header.vue'

export default {
  name: 'main',
  components: {
    Header,
    Login
  },
  data () {
    return {
      title: 'Main'
    }
  }
}
</script>

<style>
  .card--flex-toolbar {
    margin-top: -64px;
  }
  @media screen and (max-width: 599.99px) {
    .d-none {
      display: none;
    }
  }
</style>
