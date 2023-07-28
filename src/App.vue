<script>
  import MyButton from './components/MyButton.vue'
  import MyInput from './components/MyInput.vue'

  export default {
    components: {
      MyButton,
      MyInput
    },

    data() {
      return {
        username: {
          value: "User",
          error: ""
        },
        password: {
          value: "pass",
          error: ""
        }
      }
    },

    methods: {
      submit(){
        console.log("Submit")
      },

      update({ name, value, error }){
        this[name].value = value
        this[name].error = error
      }
    },

    computed: {
      valid(){
        return (
          !this.username.error && !this.password.error
        )
      }
    }
  }
</script>

<template>
  <form @submit.prevent="submit">
    <my-input name="Username"
    :value="username.value"
    :error="username.error"
    :rules="{ required: true, min: 5 }"
    @update="update"/>

    <my-input name="Password"
    type="password"
    :value="password.value"
    :error="password.error"
    :rules="{ required: true, min: 10 }"
    @update="update"/>

    <my-button background="darkslateblue" color="white" :disabled="!valid"/>
  </form>
</template>

<style scoped>
</style>
