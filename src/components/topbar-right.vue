<template>
  <div class="right">
    <img
      v-if="starDisplayed"
      src="../assets/images/MainPage_08.jpg"
      alt=""
      srcset=""
    />
    <img
      v-if="settingDisplayed"
      src="../assets/images/images/Discover_03.jpg"
      alt=""
      srcset=""
    />
  </div>
</template>

<script>
export default {
  watch: {
    current(value) {
      switch (value) {
        case 'main':
          this.settingDisplayed = false;
          this.starDisplayed = true;
          break;
        case 'search':
          this.starDisplayed = false;
          this.settingDisplayed = true;
      }
    },
  },
  inject: ['CurrentPage'],
  data() {
    return {
      current: this.CurrentPage,
      starDisplayed: true,
      settingDisplayed: false,
    };
  },
};
</script>

<style scoped>
img {
  width: 32px;
}
.right {
  margin-right: 20px;
  display: flex;
  align-items: center;
}
</style>
