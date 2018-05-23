<template>
  <div></div>
</template>

<script>
// @ is an alias to /src
import Signin from '@/components/Signin.vue'
import Header from '@/components/Header.vue'

export default {
  name: 'home',
  components: {
    Header,
    Signin
  }
}
</script>

<style>
  .card--flex-toolbar {
    margin-top: -64px;
  }
</style>
