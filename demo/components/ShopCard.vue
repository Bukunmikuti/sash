<template>
  <div class="shopcard">
    <img src="../assets/images/logo-placeholder.png" />
    <div>
      <h3>{{ props.name }}</h3>
      <p>
        {{ props.desc }}
      </p>
      <div class="props.tags">
        <span>{{ props.tags[0] }}</span
        ><span>{{ props.tags[1] }}</span
        ><span>{{ props.tags[2] }}</span>
      </div>
    </div>
  </div>
</template>

<script setup lang="js">
let props = defineProps(['name', 'desc', 'tags', 'logo'])
/* defineProps({
  name: String,
  desc: String,
  tags: [String],
  logo: {
    type: String,
    required: false
  },
}) */

const getLogo = computed(() => {
  if (props.logo) {
    return props.logo
  }
  return `logo-placeholder.png`
})
</script>

<style scoped lang="less">
.shopcard {
  max-width: 400px;
  display: flex;
  gap: 0 20px;
  border: 2px solid #ccc;
  padding: 20px;
  border-radius: 15px;
  cursor: pointer;
  &:hover {
    background: #ccc;
  }
  img {
    width: 70px;
    height: 70px;
    border-radius: 100%;
  }
  .tags {
    display: flex;
    flex-wrap: wrap;
    gap: 5px;
    word-wrap: break-word;
    margin-top: 20px;
    span {
      padding: 4px 10px;
      background: #ccc;
      font-size: 1.4rem;
      border-radius: 10px;
      background: rgb(200, 237, 239);
    }
  }
}
</style>
