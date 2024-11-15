<script>
  export default{
    data(){
      return{
        name: 'John Doe',
        status: false
      }
    }
  }
</script>

<template>
  <h1>{{ name }}</h1>
  <!-- Learn if else in Vue -->
  <p v-if="status">User is active</p>
  <p v-else="status">User is inactive</p>
</template>

