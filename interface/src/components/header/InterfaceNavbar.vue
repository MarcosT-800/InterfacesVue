<template>
    <header class="header">
      <div class="container">
        <slot name="logo"></slot>
        <nav>
          <slot name="navigation" class="navigation"></slot>
        </nav>
      </div>
    </header>
  </template>
  
  <script>
  export default {
    name: 'HeaderComponent'
  };
  </script>
  
  <style scoped>
  .header {
    background-color: transparent;
    padding: 15px 20px;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  
  .container {
    display: flex;
    align-items: center;
    gap: 10px;
  }

  .navigation {
    display: flex;
    flex-direction: row;
    justify-content: space-between;
    gap: 10px;
  }
  </style>
  