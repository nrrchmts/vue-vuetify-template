<template>
  <v-app>
    <v-container>
      <v-card>
        <v-card-title>Login</v-card-title>
        <v-form @submit.prevent="handleSubmit">
          <v-card-text>
            <v-text-field label="Username" prepend-icon="mdi-account-circle" v-model="user.username"/>
            <v-text-field label="Password" prepend-icon="mdi-lock" :type="showPassword ? 'text' : 'password'" :append-icon="showPassword ? 'mdi-eye' : 'mdi-eye-off'" @click:append="handleClick" v-model="user.password" />
          </v-card-text>
          <v-card-actions>
            <v-btn color="success" type="submit">Login</v-btn>
            <v-btn color="info">Register</v-btn>
          </v-card-actions>
        </v-form>
      </v-card>
    </v-container>
  </v-app>
</template>

<script>

export default {
  name: 'App',
  data() {
    return {
      showPassword: false,
      user: {
        username: '',
        password: ''
      }
    }
  },

  methods: {
    handleClick(){
      this.showPassword = !this.showPassword
    },
    handleSubmit(){
      console.log(this.user)
    }
  },

};
</script>
