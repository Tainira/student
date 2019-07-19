<template>
  <button class="button" @click="$emit('click', $event)">
    <span v-if="full">{{ text }}</span> ->
  </button>
</template>

<script>
export default {
  props: ['full', 'text']
}
</script>

<style scoped>
.button {
  background-color: #ebc749;
  padding: 1.8em;
  border-radius: 10px 0 0 10px;
  text-align: center;
  box-shadow: 0 0 20px grey;
}
</style>
