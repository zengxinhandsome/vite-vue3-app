<script setup>
import { ref } from 'vue';
import axios from 'axios';

let posts = ref([]);

const baseUrl = 'https://express-typeorm-demo.herokuapp.com'

axios({
  url: `${baseUrl}/posts`,
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
//   url: 'http://localhost:3001/post/create',
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
