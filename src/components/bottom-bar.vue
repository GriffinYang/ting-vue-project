<template>
  <div class="bottom-bar">
    <span @click="ChangePage('main')">
      <div class="images" @click="toggleStatus('main')">
        <img
          v-if="!status.main"
          src="../assets/images/inactive-01.png"
          alt=""
          srcset=""
        />
        <img
          v-if="status.main"
          src="../assets/images/active-01.png"
          alt=""
          srcset=""
        />
      </div>
    </span>
    <span @click="ChangePage('search')">
      <div class="images" @click="toggleStatus('search')">
        <img
          v-if="!status.search"
          src="../assets/images/inactive-02.png"
          alt=""
          srcset=""
        />
        <img
          v-if="status.search"
          src="../assets/images/active-02.png"
          alt=""
          srcset=""
        />
      </div>
    </span>
    <span @click="ChangePage('community')">
      <div class="iamges" @click="toggleStatus('community')">
        <img
          v-if="!status.community"
          src="../assets/images/inactive-03.png"
          alt=""
          srcset=""
        />
        <img
          v-if="status.community"
          src="../assets/images/active-03.png"
          alt=""
          srcset=""
        />
      </div>
    </span>
    <span @click="ChangePage('notifications')">
      <div class="images" @click="toggleStatus('notifications')">
        <img
          v-if="!status.notifications"
          src="../assets/images/inactive-04.png"
          alt=""
          srcset=""
        />
        <img
          v-if="status.notifications"
          src="../assets/images/active-04.png"
          alt=""
          srcset=""
        />
      </div>
    </span>
    <span @click="ChangePage('messages')">
      <div class="images" @click="toggleStatus('messages')">
        <img
          v-if="!status.messages"
          src="../assets/images/inactive-05.png"
          alt=""
          srcset=""
        />
        <img
          v-if="status.messages"
          src="../assets/images/active-05.png"
          alt=""
          srcset=""
        />
      </div>
    </span>
  </div>
</template>

<script>
export default {
  data() {
    return {
      status: {
        main: true,
        search: false,
        community: false,
        notifications: false,
        messages: false,
      },
    };
  },
  inject: ['ChangePage'],
  methods: {
    toggleStatus(currentObj) {
      this.status.main = false;
      this.status.search = false;
      this.status.community = false;
      this.status.notifications = false;
      this.status.messages = false;
      switch (currentObj) {
        case 'main':
          this.status.main = true;
          break;
        case 'search':
          this.status.search = true;
          break;
        case 'community':
          this.status.community = true;
          break;
        case 'notifications':
          this.status.notifications = true;
          break;
        case 'messages':
          this.status.messages = true;
      }
      console.log();
    },
  },
};
</script>

<style scoped>
.bottom-bar {
  position: fixed;
  bottom: -2px;
  width: 100%;
  display: flex;
  justify-content: space-around;
  align-items: center;
  height: 50px;
  border-top: 1px solid #d5d5d5;
  z-index: 999;
  background-color: white;
}
img {
  height: 24px;
}
</style>
