<script setup>
import {ref }from 'vue'
//composition API
  //it just like react, in react useReact but in Vue using ref
      const name= ref('John Doe');
      const status = ref('active');
      const tasks = ref(['Task One', 'Task Two', 'Task Three']);
      const newTask = ref('')

      const toggleStatus = () => {
        if(status.value ==='active'){
          status.value = 'pending';
        }else if(status.value ==='pending'){
          status.value = 'inactive';
        }else{
          status.value = 'active';
        }
      }

      const addTask = () =>{
        if(newTask.value.trim() !== ''){
          tasks.value.push(newTask.value);
          newTask.value = '';
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

  <form @submit.prevent="addTask">
    <label for="newTask">Add Task</label>
    <input type="text" id="newTask" name="newTask" v-model="newTask" />
    <button type="submit">Sumbit</button>
  </form>
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

