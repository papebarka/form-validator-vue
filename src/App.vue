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
        valid: true,
        username: {
          value: "User",
          valid: false
        },
        password: {
          value: "pass",
          valid: false
        }
      }
    },

    methods: {
      update({ name, value }){
        this[name].value = value
      }
    }
  }
</script>

<template>
  <my-input name="Username"
  :value="this.username.value"
  :rules="{ required: true, min: 5 }"
  @update="update"/>

  <my-input name="Password"
  :value="this.password.value"
  :rules="{ required: true, min: 10 }"
  @update="update"/>

  <my-button background="red" color="yellow" :disabled="!valid"/>
</template>

<style scoped>
</style>
