<template>
  <div class="content">
    <div class="content-header">
      <span
        ><img src="../assets/images/MainPage_13.jpg" alt="" srcset=""
      /></span>
      <span class="type">{{ type }}</span>
      <a href="#">See more</a>
    </div>
    <div class="content-title">
      <div class="users">
        <img :src="require(`@/assets/images/${userAvator}`)" alt="" />
      </div>
      <div class="general">
        <div class="name">{{ name }}</div>
        <span
          ><img src="../assets/images/MainPage_18.jpg" alt="" srcset=""
        /></span>
        <a href="#">@{{ shortWords }}... {{ date }}</a>
        <div class="dots">···</div>
        <div class="text-content">{{ textContent }}</div>
        <div class="tags">
          <a href="#">#{{ tag }}</a>
        </div>
      </div>
      <div class="img-content">
        <img :src="require(`@/assets/images/${img}`)" alt="" srcset="" />
      </div>
      <div class="function-bar">
        <div class="comments">
          <img src="../assets/images/MainPage_25.jpg" alt="" />
          <span>{{ comments }}</span>
        </div>
        <div class="retweet">
          <img src="../assets/images/MainPage_27.jpg" alt="" />
          <span>{{ retweeted }}</span>
        </div>
        <div class="like" @click="likeClick(likes, sentId)">
          <img src="../assets/images/MainPage_29.jpg" alt="" v-if="!isLiked" />
          <img src="../assets/images/liked.png" alt="" v-if="isLiked" />
          <span>{{ !(likes >= 1000) ? likes : translate(likes) }}</span>
        </div>
        <div class="share">
          <img src="../assets/images/MainPage_31.jpg" alt="" />
          <span>{{ shared }}</span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  emits: ['like-click'],
  props: [
    'sentId',
    'type',
    'userAvator',
    'name',
    'textContent',
    'tag',
    'date',
    'img',
    'liked',
    'retweeted',
    'comments',
    'shared',
  ],
  methods: {
    likeClick() {
      this.isLiked = !this.isLiked;
      if (this.isLiked) {
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
  computed: {
    shortWords() {
      const change = this.shortWord.slice(0, 3);
      change.toLowerCase();
      return change;
    },
  },
  data() {
    return {
      isLiked: false,
      shortWord: this.tag,
      likes: this.liked,
    };
  },
};
</script>

<style>
.img-content img {
  width: 80%;
  margin-left: 10%;
}
.tags a {
  color: #2f8ac3 !important;
  font-size: 0.625rem !important;
}
.content-title a,
.name {
  height: 13px;
  font-size: 13px;
  text-decoration: none;
}
.general span img {
  width: 0.9375rem;
  position: relative;
  top: 0.125rem;
  margin-left: 0.3125rem;
}
.name {
  font-size: 13px;
  font-family: 'Franklin Gothic Medium', 'Arial Narrow', Arial, sans-serif;
}

.content-title {
  flex-wrap: wrap;
  display: flex;
  margin-left: 5%;
}
.users {
  display: inline-block;
}
.users img {
  width: 3.1875rem !important;
}
.type {
  color: #585f65;
}
.content-header {
  display: flex;
  align-items: center;
  margin-left: 8%;
}

.content-title a,
.name {
  text-decoration: none;
}
.content-header {
  font-size: 10px !important;
}
.content-header span img {
  width: 1.25rem !important;
  height: 1.125rem !important;
}
.content {
  border-top: 1px solid #d5d5d5 !important;
  padding-bottom: 30px !important;
  padding-top: 20px !important;
}
.content-header a,
.general a {
  color: #676c6f !important;
  font-weight: bolder !important;
  text-decoration: none !important;
  margin-right: 0.125rem !important;
}
.dots {
  height: 13px !important;
  display: inline-block !important;
  align-items: center !important;
  margin-left: 0.3125rem !important;
}
.general {
  height: 0.8125rem !important;
  margin-left: 3% !important;
}
.name {
  display: inline-block !important;
}
.function-bar {
  display: flex !important;
  align-items: center !important;
  justify-content: space-around !important;
  width: 80% !important;
  position: relative !important;
  left: 10% !important;
}
.function-bar img {
  width: 1.125rem;
  height: 1rem;
}
.comments,
.retweeted,
.like,
.share {
  width: 3.25rem !important;
  height: 1.25rem !important;
}
</style>
