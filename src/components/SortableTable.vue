<script setup>
  import { computed, ref } from 'vue'

  const products = [
    { id: 1, name: 'Málna', price: 3800 },
    { id: 2, name: 'Áfonya', price: 4700 },
    { id: 3, name: 'Szeder', price: 1700 },
    { id: 4, name: 'Eper', price: 5500 },
    { id: 5, name: 'Ribizli', price: 2200 },
    { id: 6, name: 'Som', price: 1750 },
    { id: 7, name: 'Fanyarka', price: 4200 },
    { id: 8, name: 'Meggy', price: 1100 },
    { id: 9, name: 'Szilva', price: 900 },
    { id: 10, name: 'Alma', price: 750 },
    { id: 11, name: 'Barack', price: 1400 },
    { id: 12, name: 'Körte', price: 1600 },
  ]

  const sortBy = ref('id-down')

  const sortedProducts = computed(() => {
    const [field, direction] = sortBy.value.split('-')
    const sortedProducts = [...products]
    return sortedProducts.sort((a, b) => {
      if (a[field] < b[field]) {
        return direction == 'down' ? 1 : -1
      }
      if (a[field] > b[field]) {
        return direction == 'down' ? -1 : 1
      }
      return 0
    })
  })
</script>

<template>
  {{ sortBy }}
  <div>
    <table>
      <thead>
        <tr>
          <th>
            <button @click="sortBy = 'id-down'">▼</button>
            id
            <button @click="sortBy = 'id-up'">▲</button>
          </th>
          <th>
            <button @click="sortBy = 'name-down'">▼</button>
            név
            <button @click="sortBy = 'name-up'">▲</button>
          </th>
          <th>
            <button @click="sortBy = 'price-down'">▼</button>
            ár
            <button @click="sortBy = 'price-up'">▲</button>
          </th>
        </tr>
      </thead>
      <tbody>
        <tr v-for="product in sortedProducts">
          <td>{{ product.id }}</td>
          <td>{{ product.name }}</td>
          <td>
            {{
              Intl.NumberFormat('hu-HU', {
                style: 'currency',
                currency: 'HUF',
                maximumFractionDigits: 0,
              }).format(product.price)
            }}
          </td>
        </tr>
      </tbody>
    </table>
  </div>
</template>

<style scoped>
  div {
    background-color: #fff;
    width: 80vw;
    margin: 0 auto;
    display: flex;
    justify-content: center;
  }
  table {
    width: 100%;
    border-collapse: collapse;
  }
  thead,
  button {
    background-color: #01200f;
    color: #fff;
    border: none;
  }
  th {
    padding: 1em;
  }
  td {
    width: 20vw;
    padding: 0.75em;
  }
  tbody tr:nth-child(odd) {
    background-color: #9ec5ab;
  }
</style>
