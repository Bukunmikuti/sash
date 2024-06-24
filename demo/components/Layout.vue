<template>
  <div id="container">
    <div id="sidebar">
      <div class="view" ref="feed" @click="toView('feed')">
        <Icon name="fluent:feed-32-regular" size="40px" />
        <p>Feed</p>
      </div>
      <div class="view" ref="search" @click="toView('search')">
        <Icon name="mdi:store-search" size="40px" />
        <p>Search</p>
      </div>
      <div class="view" ref="profile" @click="toView('profile')">
        <Icon name="iconamoon:profile-circle" size="40px" />
        <p>Profile</p>
      </div>
    </div>
    <div id="main">
      <slot></slot>
    </div>
  </div>
</template>

<script setup lang="js">
const feed = ref(null);
const search = ref(null);
const profile = ref(null);

let toView = (view) => {
  removeViews();
  if (view === "feed") {
    feed.value.classList.add("active");
  } else if (view === "search") {
    search.value.classList.add("active");
  } else if (view === "profile") {
    profile.value.classList.add("active");
  }
};

let removeViews = () => {
  feed.value.classList.remove("active");
  search.value.classList.remove("active");
  profile.value.classList.remove("active");
};
</script>

<style scoped lang="less">
#container {
  width: 100%;
  height: 100dvh;
  display: grid;
  grid-template-columns: auto 1fr;
  position: fixed;

  #main {
    position: relative;
    overflow-y: scroll;
  }
}

#sidebar {
  width: 200px;
  height: 100%;
  background: #e0e0e0;
  border-right: 1px solid #ccc;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  gap: 40px 0;

  .view {
    display: flex;
    justify-content: center;
    align-items: center;
    flex-direction: column;
    align-items: center;
    cursor: pointer;

    p {
      font-size: 1.6rem;
      padding: 5px 30px;
      margin-top: 7px;
      border-radius: 30px;
    }

    &.active {
      p {
        font-weight: 500;
        background: lightgray;
      }
    }
  }
}
</style>
