<script>
    export default {
        props: {
            name: {
                type: String,
                required: true
            },
            rules: {
              //min: number
              //required: boolea
              type: Object,
              default: {}
            }
        },
        
        methods: {
        },

        data(){
          return {
            value: ''
          }
        },

        computed: {
          error(){
            if(this.rules.required && this.value.length === 0){
              return 'Value is required'
            }

            if(this.rules.min && this.value.length < this.rules.min){
              return `The minimum length is ${this.rules.min}`
            }
          }
        }
    }
</script>

<template>
    <div class="label">
      <label :for="name">{{ name }}</label>
      <div class="error">{{ error }}</div>
    </div>
    <input type="text" :id="username" v-model="value"/>
</template>

<style scoped></style>