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
      <function-bar></function-bar>
    </div>
  </div>
</template>

<script>
import FunctionBar from './function-bar.vue';
export default {
  components: { FunctionBar },
  props: [
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
  provide() {
    return {
      retweeted: this.retweeted,
      likes: this.liked,
      comments: this.comments,
      shared: this.shared,
    };
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
      shortWord: this.tag,
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
  width: 3.1875rem;
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
  font-size: 10px;
}
.content-header span img {
  width: 1.25rem;
  height: 1.125rem;
}
.content {
  border-top: 1px solid #d5d5d5;
  padding-bottom: 30px;
  padding-top: 20px;
}
.content-header a,
.general a {
  color: #676c6f;
  font-weight: bolder;
  text-decoration: none;
  margin-right: 0.125rem;
}
.dots {
  height: 13px;
  display: inline-block;
  align-items: center;
  margin-left: 0.3125rem;
}
.general {
  height: 0.8125rem;
  margin-left: 3%;
}
.name {
  display: inline-block;
}
</style>
