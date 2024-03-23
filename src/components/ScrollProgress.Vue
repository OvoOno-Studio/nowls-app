<template>
    <div class="progress-bar" :style="{ width: progress + '%' }"></div>
  </template>
  
  <script>
  export default {
    props: {
      progress: {
        type: Number,
        required: true
      }
    }
  };
  </script>
  
  <style>
  .progress-bar {
    height: 10px;
    background-color: blue; /* You can customize the color */
  }
  </style>
  