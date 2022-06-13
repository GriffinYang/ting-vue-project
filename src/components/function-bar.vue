<template>
  <div class="function-bar">
    <div class="comments">
      <img src="../assets/images/MainPage_25.jpg" alt="" />
      <span>{{ comments }}</span>
    </div>
    <div class="retweet">
      <img src="../assets/images/MainPage_27.jpg" alt="" />
      <span>{{ retweeted }}</span>
    </div>
    <div class="like" @click="likeClick">
      <img src="../assets/images/MainPage_29.jpg" alt="" v-if="!liked" />
      <img src="../assets/images/liked.png" alt="" v-if="liked" />
      <span>{{ !(likes >= 1000) ? likes : translate(likes) }}</span>
    </div>
    <div class="share">
      <img src="../assets/images/MainPage_31.jpg" alt="" />
      <span>{{ shared }}</span>
    </div>
  </div>
</template>

<script>
export default {
  inject: ['likes', 'retweeted', 'comments', 'shared'],
  data() {
    return {
      liked: false,
    };
  },
  methods: {
    likeClick() {
      this.liked = !this.liked;
      if (this.liked) {
        this.likes++;
      } else {
        this.likes--;
      }
    },
    translate(num) {
      const num1 = num / 1000;
      const num2 = (num / 100) % 10;
      return `${num1},${num2}k`;
    },
  },
};
</script>

<style scoped>
.function-bar {
  display: flex;
  align-items: center;
  justify-content: space-around;
  width: 80%;
  position: relative;
  left: 10%;
}
img {
  width: 1.125rem;
  height: 1rem;
}
.comments,
.retweeted,
.like,
.share {
  width: 3.25rem;
  height: 1.25rem;
}
</style>
