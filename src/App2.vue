<script>
  export default{
    data(){
      return{
        name: 'John Doe',
        status: 'active',
        tasks: ['Task One', 'Task Two', 'Task Three'],
        link: 'https://google.com'
      }
    },
    methods:{
      toggleStatus(){
        if(this.status ==='active'){
          this.status = 'pending';
        }else if(this.status ==='pending'){
          this.status = 'inactive';
        }else{
          this.status = 'active';
        }
      }
    }
  }
</script>

<template>
  <h1>{{ name }}</h1>
  <!-- Learn if else in Vue in bolean-->
  <!-- <p v-if="status">User is active</p>
  <p v-else="status">User is inactive</p> -->
  <!-- Learn if else when the value is string -->
  <p v-if="status === 'active'">User is active</p>
  <p v-else-if="status === 'pending'">User is pending</p>
  <p v-else="status">User is inactive</p>

  <h3>Tasks:</h3>
  <ul>
    <li v-for="task in tasks" :key="task">{{ task }}</li>
  </ul>
  <!-- So v-bind it's for the value data -->
  <a v-bind:href="link">Click for google</a>
  <br/>
  <!-- there are two way to call onclick either v-on:click or @click -->
  <!-- <button v-on:click="toggleStatus">Change status</button> -->
  <button @click="toggleStatus">Change status</button>
</template>

