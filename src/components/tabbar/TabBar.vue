<template>
  <div id="tab-bar">
    <slot></slot>
  </div>
</template>

<script>
  export default {
    name: "TabBar"
  }
</script>

<style scoped>
  #tab-bar{
    position: fixed;
    bottom: 0;
    left: 0;
    right: 0;
    display: flex;
    background:#dadada;
  }
</style>
