<template>
  <table class="table">
    <tbody>
      <tr v-for="item in items" :key="item.id">
        <td class="pic"><img :src="item.image" /></td>
        <td class="amount">{{ item.amount }}</td>
        <td class="x">&times;</td>
        <td class="name">{{ item.name }}</td>
        <td class="price">{{ item.price }}</td>
      </tr>
    </tbody>
  </table>
</template>

<script>
export default {
  props: ['items', 'image']
}
</script>

<style scoped>
.table {
  width: 100%;
}
.pic {
  max-width: 30%;
}
.price {
  color: grey;
}
</style>
