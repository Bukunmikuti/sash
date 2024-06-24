<template>
  <div class="shopcard">
    <img src="../assets/images/logo1.jpg" />
    <div>
      <h3>Zara Stores</h3>
      <p>
        Zara stores is a fashion-forward brand offering an exclusive range of
        stylish clothing and accessories for modern women, combining elegance
        with comfort.
      </p>
      <div class="tags">
        <span>Clothing</span><span>Women dress</span><span>Fashion</span>
      </div>
    </div>
  </div>
</template>

<script setup></script>

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
