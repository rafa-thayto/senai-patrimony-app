<template>
  <div>

    <!-- <v-container>
    </v-container> -->
    <!-- <v-card flat> -->
      <v-toolbar dark color="primary" flat extended>
        <v-toolbar-side-icon></v-toolbar-side-icon>
        <v-toolbar-title>{{ title }}</v-toolbar-title>
        <v-spacer></v-spacer>
        <a style="color: white"><h1>Não tem conta ainda?</h1></a>
      </v-toolbar>
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
              <Signin />
            </v-card-text>

          </v-card>
        </v-flex> -->
      <!-- </v-layout> -->
    <!-- </v-card> -->
    <v-container>
      <v-layout row>
        <v-flex xs12 sm6 offset-sm3>
          <v-card class="card--flex-toolbar">
            <v-card-text style="height: 100%;">
              <v-container>
                <Signin />
              </v-container>
            </v-card-text>
          </v-card>
        </v-flex>
      </v-layout>
    </v-container>

  </div>
</template>

<script>
// @ is an alias to /src
import Signin from '@/components/Signin.vue'
import Header from '@/components/Header.vue'

export default {
  name: 'main',
  components: {
    Header,
    Signin
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
