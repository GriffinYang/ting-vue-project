<template>
  <top-bar></top-bar>
  <text-content
    v-for="user in users"
    :key="user.avator"
    :type="user.type"
    :userAvator="user.userAvator"
  ></text-content>
  <bottom-bar></bottom-bar>
</template>

<script>
import TopBar from './components/top-bar.vue';
import BottomBar from './components/bottom-bar.vue';
import TextContent from './components/text-content.vue';
import { computed } from 'vue';
export default {
  data() {
    return {
      currentPage: 'main',
      users: {
        users: {
          type: 'Video games·',
          userAvator: '../assets/images/MainPage_16.jpg',
        },
      },
    };
  },
  components: {
    TopBar,
    BottomBar,
    TextContent,
  },
  methods: {
    changeCurrent(current) {
      this.currentPage = current;
    },
  },
  provide() {
    return {
      ChangePage: this.changeCurrent,
      CurrentPage: computed(() => this.currentPage),
    };
  },
};
</script>

<style></style>
