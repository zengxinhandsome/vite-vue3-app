<script setup>
import { ref } from 'vue';
import axios from 'axios';
import { REQUEST_URL } from '../constants';

let posts = ref([]);

// console.log('import.meta.env: ', import.meta.env.VITE_SOME_KEY);

axios({
  url: `${REQUEST_URL}/posts`,
  method: 'GET'
}).then(({ data }) => {
  posts.value = data;
});

// axios({
//   url: 'http://localhost:3001/posts/update/2',
//   method: 'PUT',
//   data: {
//     title: '修改 title',
//     content: '修改 content'
//   }
// }).then(({ data }) => {
//   console.log('data: ', data);
// });

// axios({
//   url: `${REQUEST_URL}/post/create`,
//   method: 'POST',
//   data: {
//     title: 'My first title',
//     content: 'post content'
//   }
// }).then(({ data }) => {
//   console.log('data: ', data);
// });
</script>

<template>
  <div>{{ posts }}</div>
</template>
