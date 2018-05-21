<template>
  <v-content>

    <form>
      <!-- Email -->
      <v-text-field
        v-model="email"
        label="E-mail"
        :error-messages="emailErrors"
        required
        @input="$v.email.$touch()"
        @blur="$v.email.$touch()"
      ></v-text-field>
      <!-- Password -->
      <v-text-field
        v-model="password"
        label="Senha"
        :append-icon="passwordNotVisible ? 'visibility' : 'visibility_off'"
        :append-icon-cb="() => (passwordNotVisible = !passwordNotVisible)"
        :error-messages="passwordErrors"
        :counter="20"
        :type="passwordNotVisible ? 'password' : 'text'"
        required
        min="6"
        @input="$v.password.$touch()"
        @blur="$v.password.$touch()"
      ></v-text-field>

      <v-btn @click="submit">submit</v-btn>
    </form>

  </v-content>
</template>

<script>
import { validationMixin } from 'vuelidate'
import { required, maxLength, email } from 'vuelidate/lib/validators'

export default {
  mixins: [validationMixin],
  name: 'login',
  validations: {
    email: { required, email },
    password: { required, maxLength: maxLength(20) }
  },
  data () {
    return {
      email: '',
      password: '',
      passwordNotVisible: true
    }
  },
  computed: {
    emailErrors () {
      const errors = []
      if (!this.$v.email.$dirty) return errors
      !this.$v.email.email && errors.push('Coloque um e-mail válido')
      !this.$v.email.required && errors.push('E-mail é obrigatório')
      return errors
    },
    passwordErrors () {
      const errors = []
      if (!this.$v.password.$dirty) return errors
      !this.$v.password.maxLength && errors.push('A senha deve ter entre 6 e 20 caracteres')
      !this.$v.password.required && errors.push('Senha é obrigatória')
      return errors
    }
  },
  methods: {
    submit () {
      this.$v.$touch()
      // fetch('http://localhost:8080/ianesws/v1/usuarios/auth').
      fetch('http://localhost:8080/ianesws/v1/usuarios/auth', {
        method: 'POST',
        headers: new Headers({
          'Content-Type': 'application/json'
        }),
        body: JSON.stringify({
          email: this.email,
          senha: this.password
        })
      }).then((res) => console.log(res))
        .catch((e) => console.log(`Error: ${e}`))
    }
  }
}
</script>

<style>

</style>
