<script setup>
import { ref } from 'vue'
import ProductList from '@/components/ProductList.vue'
import ProductsAdd from '@/components/ProductsAdd.vue'

const produtos = ref([
  { id: 1, nome: 'Produto 1', preco: 'R$20,50' },
  { id: 2, nome: 'Produto 2', preco: 'R$120,50' },
  { id: 3, nome: 'Produto 3', preco: 'R$220,50' },
  { id: 4, nome: 'Produto 4', preco: 'R$320,50' }
])

const proxId = ref(5)

function excluirItem(id) {
  const index = produtos.value.findIndex((produto) => produto.id === id)
  produtos.value.splice(index, 1)
}

function excluirtodos() {
  produtos.value = []
}

function adicionarProdutos(produto) {
  produto.id = proxId
  produtos.value.push(produto)
  proxId.value++
}
</script>

<template>
  <h1>Meus produtos</h1>
  <products-add @adicionar="adicionarProdutos" />
  <product-list :produtos="produtos" @excluir="excluirItem" @excluirtodos="excluirtodos" />
</template>

<style scoped>
</style>
