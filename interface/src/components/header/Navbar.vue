<template>
    <div id="app">
      <HeaderComponent>
        <template #logo>
          <h1>Minha Aplicação</h1>
        </template>
        <template #navigation>
        <nav>
            <a href="#">Página Inicial</a>
            <a href="#">Sobre</a>
            <a href="#">Contato</a>
        </nav>
        </template>
      </HeaderComponent>
      <main>
        </main>
    </div>
  </template>
  
  <script>
  import HeaderComponent from './InterfaceNavbar.vue';
  
  export default {
    components: {
      HeaderComponent
    }
  };
  </script>

<style>

  h1 {
    font-size: 28px;
  }
  nav {
    display: flex;
    gap: 10px;
    align-items: center;
  }
</style>
  