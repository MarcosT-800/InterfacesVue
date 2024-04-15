<template>
  <button
    :type="type"
    :class="{ 'primary': type === 'primary', 'secondary': type === 'secondary' }"
  >
    <slot>{{ label }}</slot>
  </button>
</template>

<script>
export default {
  props: {
    type: {
      type: String,
      default: 'primary'
    },
    label: {
      type: String,
      required: true
    }
  }
};
</script>

<style scoped>
.button {
  padding: 10px 20px;
  border: none;
  border-radius: 5px;
  cursor: pointer;
}

.primary {
  background-color: #007bff;
  color: #fff;
}

.secondary {
  background-color: #6c757d;
  color: #fff;
}
</style>
