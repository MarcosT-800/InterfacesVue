<template>
  <table class="custom-table">
    <thead>
      <tr>
        <slot name="header"></slot>
      </tr>
    </thead>
    <tbody>
      <tr v-for="(item, index) in items" :key="index">
        <slot name="body-row" :item="item"></slot>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  props: {
    items: {
      type: Array,
      required: true
    }
  }
};
</script>

<style scoped>
.custom-table {
  width: 100%;
  border-collapse: collapse;
  background-color: #ffffff;
  color: #333333;
}

.custom-table th,
.custom-table td {
  padding: 12px;
  border: 1px solid #dddddd;
  text-align: left;
}

.custom-table th {
  background-color: #f2f2f2;
}

.custom-table tbody tr:nth-child(even) {
  background-color: #f9f9f9;
}

.custom-table tbody tr:hover {
  background-color: #e9e9e9;
}
</style>
