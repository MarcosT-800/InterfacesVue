<template>
  <div>
    <table-component :items="tableData">
      <template #header>
        <th>Nome</th>
        <th>Idade</th>
        <th>Cidade</th>
      </template>
      <template #body-row="{ item }">
        <td>{{ item.name }}</td>
        <td>{{ item.age }}</td>
        <td>{{ item.city }}</td>
      </template>
    </table-component>
  </div>
</template>

<script>
import TableComponent from './interfaceTable.vue';

export default {
  name: 'LittleTable',
  components: {
    TableComponent
  },
  data() {
    return {
      tableData: [
        { name: 'João', age: 30, city: 'São Paulo' },
        { name: 'Maria', age: 25, city: 'Rio de Janeiro' },
        { name: 'Pedro', age: 40, city: 'Belo Horizonte' }
      ]
    };
  }
};
</script>
