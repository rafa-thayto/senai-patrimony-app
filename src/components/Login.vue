<template>
  <v-content>
    <form>
      <v-text-field
        v-model="email"
        :error-messages="emailErrors"
        label="E-mail"
        required
        @input="$v.email.$touch()"
        @blur="$v.email.$touch()"
      ></v-text-field>
      <v-text-field
        v-model="password"
        :error-messages="passwordErrors"
        label="Senha"
        required
        @change="$v.password.$touch()"
        @blur="$v.password.$touch()"
      ></v-text-field>

      <v-btn @click="submit">submit</v-btn>
      <v-btn @click="clear">clear</v-btn>
    </form>
  </v-content>
</template>

<script>
import { validationMixin } from 'vuelidate'
import { required, maxLength, email } from 'vuelidate/lib/validators'
import axios from 'axios'

export default {
  mixins: [validationMixin],
  name: 'login',
  data: () => ({
    password: '',
    email: ''
  }),
  computed: {

  },
  methods: {
    submit () {
      this.$v.$touch()
      axios.post('http://localhost:8080/v1/usuarios/auth', {
        email: this.email,
        senha: this.password
      })
    },
    clear () {
      this.$v.$reset()
    }
  }
}
</script>

<style>

</style>
