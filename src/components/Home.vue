  <script>
  export default {
    data() {
      return {
        userName: '',
      };
    },
    created() {
      // Retrieve the user name from localStorage or state management
      this.userName = localStorage.getItem('userName') || 'Guest';
    },
  };
  </script>
<template>
    <div class="home">
      <h2>Welcome To Auth Login and Register project hope you like it , {{ userName }} 😉😊!</h2>
    </div>
  </template>
  
  
  <style lang="scss" scoped>
    h2{
        text-align: center;
        margin-top: 3rem;
    }
  </style>
  