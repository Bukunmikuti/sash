<template>
  <div id="container">
    <div id="main">
      <swiper-container
        slides-per-view="1"
        speed="500"
        space-between="10"
        loop="true"
        navigation="true"
        pagination="true"
      >
        <swiper-slide class="slide">
          <img src="../assets/images/fashion2.jpg" />
        </swiper-slide>
        <swiper-slide class="slide">
          <img src="../assets/images/fashion.png" />
        </swiper-slide>
      </swiper-container>

      <div id="brand-info">
        <div class="name">
          <img src="../assets/images/zara.jpg" />
          <div class="under">
            <h2>Zara Stores</h2>
            <Button label="Follow Store" severity="secondary" />
          </div>
        </div>
        <div class="desc">
          <h5>Description</h5>
          <p>
            Zara stores is a fashion-forward brand offering an exclusive range
            of stylish clothing and accessories for modern women, combining
            elegance with comfort. We make you elegant, classy and always a
            spec.
          </p>
        </div>
        <div class="product">
          <div class="card">
            <img src="../assets/images/pr1.jpg" />
            <p class="name">Slim Classy Gown</p>
            <p class="cost">Price: ₦8,950</p>
            <Button>Shop now</Button>
          </div>
          <div class="card">
            <img src="../assets/images/pr2.jpg" />
            <p class="name">Slim Classy Gown</p>
            <p class="cost">Price: ₦8,950</p>
            <Button>Shop now</Button>
          </div>
          <div class="card">
            <img src="../assets/images/pr3.jpg" />
            <p class="name">Asymetric Women Skirt flora</p>
            <p class="cost">Price: ₦5,300</p>
            <Button>Shop now</Button>
          </div>
          <div class="card">
            <img src="../assets/images/pr4.jpg" />
            <p class="name">Assymetric Women Skirt black</p>
            <p class="cost">Price: ₦5,900</p>
            <Button>Shop now</Button>
          </div>
          <div class="card">
            <img src="../assets/images/pr5.jpg" />
            <p class="name">Gean Women Skirt</p>
            <p class="cost">Price: ₦6,900</p>
            <Button>Shop now</Button>
          </div>
        </div>
      </div>
    </div>
    <div id="leftbar"></div>
  </div>
</template>

<script setup lang="js">
import Button from 'primevue/button';
import { register } from 'swiper/element/bundle';
register();
</script>

<style scoped lang="less">
#container {
  #main {
    width: 100%;
    //background: teal;
  }
}

.slide {
  width: 100%;
  height: 350px;

  img {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
}

#brand-info {
  width: 100%;
  margin: 20px;
  padding-left: 10px;

  h5 {
    font-size: 1.7rem;
  }
  .name {
    display: flex;
    align-items: center;
    gap: 20px;
    img {
      width: 80px;
      height: 80px;
      border-radius: 100%;
    }
    h2 {
      font-size: 2.5rem;
    }
  }

  .desc {
    max-width: 500px;
    margin-top: 20px;
  }

  .product {
    width: 100%;
    display: grid;
    grid-template-columns: auto auto;
    gap: 10px;
    margin-top: 30px;

    @media @desktop {
      grid-template-columns: auto auto auto;
    }

    .card {
      width: 200px;
      border-radius: 10px;
      border: 1px solid #ccc;
      text-align: center;

      img {
        width: 200px;
        height: 200px;
        object-fit: cover;
      }

      .name {
        width: fit-content;
        text-align: center;
        font-weight: 700;
      }
    }
  }
}
</style>
