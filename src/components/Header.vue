<template>
  <div class="header-top">
    Yu-Gi-Oh API
  </div>
  <header class="app-header">
    <h1>Cards Found : vedi infondo</h1>
  </header>
</template>

<script>
export default {
  name: "Header",
};
</script>

<style scoped>
.app-header {
  background-color: #333;
  color: white;
  padding: 1rem;
  text-align: center;
  margin-bottom: 40px;
}

.header-top {
  background-color: white;
  height: 80px;
  display: flex;
  align-items: center;
  padding-left: 20px;
  font-size: 24px;
  font-weight: bold;
  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
}
</style>
