<template>
  <div>
    <h2>This is a popup</h2>
      <button @click="$emit('close')">close</button>
  </div>
</template>

<script>
export default {
  name: "Popup",
  emits: ['close'],
};
</script>

<style scoped>
</style>