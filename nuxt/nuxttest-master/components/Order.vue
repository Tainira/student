<template>
  <div
    class="order"
    :class="{
      order_white: white
    }"
  >
    <img :src="avatar" />
    <div>{{ name }}</div>
    <div>{{ price }}</div>
    <ul class="images">
      <li v-for="(photo, index) in photos" :key="index" class="images-item">
        <img :src="photo" class="image" />
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  props: ['avatar', 'name', 'price', 'photos', 'white']
}
</script>

<style scoped lang="postcss">
.order {
  padding: 10px;
  background-color: black;
  color: white;
  border-radius: 10px;
  text-align: center;
  box-shadow: 0 0 20px grey;
}

.order_white {
  background-color: white;
  color: black;
}

.images {
  margin: 0;
  padding: 0;
}

.image {
  max-width: 100%;
  height: auto;
}

.images-item {
  display: block;
}
</style>
