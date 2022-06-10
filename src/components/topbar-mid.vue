<template>
  <div class="mid">
    <img
      v-if="twitterDisplay"
      class="twitter-logo"
      src="../assets/images/MainPage_06.jpg"
      alt=""
    />
    <div class="search-bar" v-if="searchDisplay">
      <input type="text" placeholder="Search Twitter" />
      <span>
        <img
          id="search-img"
          src="../assets/images/images/Discover_06.jpg"
          alt=""
          srcset=""
        />
      </span>
    </div>
  </div>
</template>

<script>
export default {
  watch: {
    current(value) {
      switch (value) {
        case 'main':
          this.searchDisplay = false;
          this.twitterDisplay = true;
          break;
        case 'search':
          this.twitterDisplay = false;
          this.searchDisplay = true;
      }
    },
  },
  inject: ['CurrentPage'],
  data() {
    return {
      current: this.CurrentPage,
      twitterDisplay: true,
      searchDisplay: false,
    };
  },
};
</script>

<style scoped>
.twitter-logo {
  width: 32px;
  height: 25px;
}
.mid {
  display: flex;
  align-items: center;
}
input {
  width: 250px;
  background-color: #eef2f3;
  border: 0px;
  height: 1.75rem;
  border-radius: 15px;
  text-align: center;
  outline: none;
}
#search-img {
  height: 1.25rem;
  position: absolute;
  right: 63%;
  top: 15px;
}
</style>
