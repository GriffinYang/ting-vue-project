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
        <img :src="userAvator" alt="" />
      </div>
      <div class="general">
        <div class="name">Assasin's Creed</div>
        <span
          ><img src="../assets/images/MainPage_18.jpg" alt="" srcset=""
        /></span>
        <a href="#">@ass...· 5/19/22</a>
        <div class="dots">···</div>
        <div class="text-content">Time to test your loyalty.</div>
        <div class="tags">
          <a href="#">#AssasinsCreed</a>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: ['type', 'userAvator'],
};
</script>

<style>
.content {
  width: 100%;
  min-height: 1000px;
  z-index: 5px;
  margin-top: 53px;
}
</style>
