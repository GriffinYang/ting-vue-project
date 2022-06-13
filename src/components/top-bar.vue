<template>
  <div class="topbar">
    <top-left></top-left>
    <top-mid></top-mid>
    <top-right></top-right>
  </div>
</template>

<script>
import TopLeft from './topbar-left.vue';
import TopMid from './topbar-mid.vue';
import TopRight from './topbar-right.vue';

export default {
  components: {
    TopLeft,
    TopMid,
    TopRight,
  },
};
</script>

<style scoped>
.topbar {
  height: 50px;
  display: flex;
  justify-content: space-between;
  border-bottom: 1px solid #d5d5d5;
  position: fixed;
  top: 0px;
  width: 100%;
  z-index: 999;
  background-color: white;
}
</style>
