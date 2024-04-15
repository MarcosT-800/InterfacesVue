<template>
    <div id="app">
      <card hasShadow>
        <template #header>
          <h3>Produto em Destaque</h3>
        </template>
        <img src="..." alt="Imagem do Produto" class="img-fluid mb-2">
        <p>Descrição do produto em destaque.</p>
        <template #footer>
          <a href="#" class="btn btn-primary">Ver Detalhes</a>
        </template>
      </card>
      <card>
        <h3>Notícias Recentes</h3>
        <ul>
          <li>Notícia 1</li>
          <li>Notícia 2</li>
          <li>Notícia 3</li>
        </ul>
      </card>
    </div>
  </template>
  
  <script>
  import CardComponent from './InterfaceCard.vue';
  
  export default {
    components: {
      CardComponent
    }
  };
  </script>
  