<template>
    <nav class="navbar">
      <div class="navbar-content">
        <h1>Ashley Earl Law Firm</h1>
        <p>Call: 2257619456</p>
      </div>
    </nav>
  </template>
 
  <script>
  export default {
    name: 'NavbarView',
  }
  </script>
 
  <style scoped>
  .navbar {
    position: fixed;
    top: 0;
    left: 0;
    width: 100%;
    height: 60px;
    background-color: #333;
    z-index: 9999;
  }
 
  .navbar-content {
    max-width: 800px;
    margin: 0 auto;
    height: 100%;
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 0 20px;
    color: #fff;
  }
 
  .navbar-content h1 {
    font-size: 1.2em;
    margin: 0;
  }
 
  .navbar-content p {
    margin: 0;
  }
  </style>