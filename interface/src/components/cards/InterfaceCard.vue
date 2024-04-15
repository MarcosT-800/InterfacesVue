<template>
  <div class="ui-card" :class="{ 'ui-card--shadow': hasShadow }">
    <slot name="header"></slot>
    <div class="ui-card__body">
      <slot />
    </div>
    <slot name="footer"></slot>
  </div>
</template>

<script>
export default {
  props: {
    hasShadow: {
      type: Boolean,
      default: false
    }
  }
};
</script>

<style scoped>
.ui-card {
  background-color: #ffffff;
  border: 1px solid white;
  border-radius: 10px;
  padding: 20px;
  margin-bottom: 20px;
  transition: box-shadow 0.3s ease;
}

.ui-card--shadow {
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}

.ui-card__body {
  margin-top: 15px;
}

/* Adicionando estilos para o cabeçalho e rodapé se necessário */
.ui-card__header {
  font-size: 1.25rem;
  font-weight: bold;
  margin-bottom: 15px;
}

.ui-card__footer {
  margin-top: 15px;
  text-align: right;
}

/* Adicione mais estilos conforme necessário para se adequar ao seu design */
</style>
