<template>
  <div class="card">
    <h2>{{ content }}</h2>

    <div id="card-header">
      <slot name="header"></slot>
    </div>
    <div id="card-content">
      <!-- one slot can be unnamed it will be consider as default -->
      <slot></slot>
    </div>
    <div id="card-footer">
      <slot name="footer"></slot>
    </div>
  </div>
</template>

<script>
export default {
  name: "Card",
  props: ["content"],
};
</script>

<style scoped>
.card {
  border: 1px solid #ddd;
  padding: 20px;
  width: 300px;
  margin: auto;
  margin-bottom: 5px;
}
</style>