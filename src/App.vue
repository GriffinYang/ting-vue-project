<template>
  <top-bar></top-bar>
  <div class="main-content">
    <text-content
      v-for="user in users"
      :type="user.type"
      :key="user.id"
      :name="user.name"
      :userAvator="user.avator"
      :textContent="user.textContent"
      :date="user.date"
      :tag="user.tag"
      :img="user.photo"
      :liked="user.liked"
      :retweeted="user.retweeted"
      :shared="user.shared"
      :comments="user.comments"
      @like-click.prevent="updateLikes"
    ></text-content>
  </div>
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
        user1: {
          id: 1,
          sentId: 202261782451,
          type: 'Video games·',
          avator: 'MainPage_16.jpg',
          name: "Assasin's Creed",
          textContent: 'Time to test your loyalty.',
          tag: "Assasin'sCreed",
          date: '5/19/22',
          photo: 'MainPage_23.jpg',
          liked: 999,
          retweeted: 999,
          shared: 999,
          comments: 999,
        },
        user2: {
          id: 2,
          sentId: 2022617824533,
          type: 'Video games',
          avator: 'MainPage_16.jpg',
          name: "Assasin's Creed",
          textContent: 'Time to test your loyalty.',
          tag: "Assasin'sCreed",
          date: '5/19/22',
          photo: 'MainPage_23.jpg',
          liked: 999,
          retweeted: 999,
          shared: 999,
          comments: 999,
        },
        user3: {
          id: 2,
          sentId: 2022617522,
          type: 'Video games',
          avator: 'MainPage_16.jpg',
          name: "Assasin's Creed",
          textContent: 'Time to test your loyalty.',
          tag: "Assasin'sCreed",
          date: '5/19/22',
          photo: 'MainPage_23.jpg',
          liked: 999,
          retweeted: 999,
          shared: 999,
          comments: 999,
        },
        user4: {
          id: 2,
          sentId: 2022617522,
          type: 'Video games',
          avator: 'MainPage_16.jpg',
          name: "Assasin's Creed",
          textContent: 'Time to test your loyalty.',
          tag: "Assasin'sCreed",
          date: '5/19/22',
          photo: 'MainPage_23.jpg',
          liked: 999,
          retweeted: 999,
          shared: 999,
          comments: 999,
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
    updateLikes(likes, id) {
      this.users.find((user) => user.id == id).liked = likes;
    },
  },
  provide() {
    return {
      Users: this.users,
      ChangePage: this.changeCurrent,
      CurrentPage: computed(() => this.currentPage),
    };
  },
};
</script>

<style scoped>
.main-content {
  margin-top: 3.125rem;
}
</style>
