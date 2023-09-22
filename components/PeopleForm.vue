<template>
  <h1 class="mb-20">people</h1>
  <h3>list out people, jobs in the creative industry. not just games + animation. anyone who needs to be creative to do their work (visually or otherwise). </h3>
  <h3 class="mb-20">Format like 'Name - Job Title'</h3>
  <div>
    <form @submit="onSubmit">
      <input type="text" v-model="message" placeholder="Enter name here" class="p-2" />
      <button type="submit" class="m-4 bg-white text-black px-4 py-2">Submit</button>
    </form>
  </div>
  <div>
    <ul>
      <li v-for="item in items" :key="item" class="list-none">{{ item }}</li>
  </ul>    
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue'


const items = ref([] as string[]);
const message = ref('');

const onSubmit = (e: Event) => {
  e.preventDefault()
  console.log({"message.value": message.value})
  items.value.push(message.value)
  message.value = "";
}

</script>