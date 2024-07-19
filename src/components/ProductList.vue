<script setup>
defineProps(['produtos'])
</script>
<template>
  <table>
    <thead>
      <tr>
        <th>Nome</th>
        <th>Preço</th>
        <th>Ações</th>
      </tr>
    </thead>
  </table>
  <tbody>
    <tr v-for="produto in produtos" :key="produto.id">
      <td>{{ produto.nome }}</td>
      <td>{{ produto.preco }}</td>
      <td>
        <i class="mdi mdi-delete" @click="$emit('excluir', produto.id)"></i>
      </td>
    </tr>
    <button @click="$emit('excluirtodos')">Apagar tudo</button>
  </tbody>
</template>

<style scoped>
td,
th {
  padding: 5px;
}
</style>
