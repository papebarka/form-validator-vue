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
          input($event){
            this.value = $event.target.value
          }
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
          }
        }
    }
</script>

<template>
    <div class="label">
      <label :for="name">{{ name }}</label>
      <div class="error">{{ error }}</div>
    </div>
    <input type="text" :id="username" :value="value" @input="input"/>
</template>

<style scoped></style>