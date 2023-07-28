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
        valid: true
      }
    }
  }
</script>

<template>
  <my-input name="Username"
  :rules="{ required: true, min: 5 }"/>
  <my-button background="red" color="yellow" :disabled="!valid"/>
</template>

<style scoped>
</style>
