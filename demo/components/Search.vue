<template>
  <div id="container">
    <div id="search-header">
      <h1>What do you want to get today?</h1>
      <InputGroup id="input-group">
        <inputText
          id="search-box"
          placeholder="I need some white sneakers"
          v-model="searchparam"
          @keyup.enter="powersearch"
        />
        <!-- <Button id="search-btn" type="button" label="Search" icon="pi pi-search" /> -->
        <Icon
          @click="powersearch"
          id="search-btn"
          name="iconamoon:search-bold"
          size="35px"
        ></Icon>
      </InputGroup>
    </div>

    <div id="search-result">
      <ShopCard
        v-for="store in allStores"
        :name="store.name"
        :desc="store.desc"
        :tags="store.tags"
        :logo="store.logo"
        :key="store.name"
        @click="toShop"
      ></ShopCard>
    </div>
  </div>
</template>

<script setup lang="js">
import 'primevue/resources/themes/aura-light-green/theme.css'
//import { stores } from '#imports'
import { searchindex, stores } from '#imports'

const searchparam = ref(null)
const allStores = ref()

const powersearch = () => {
  console.log(searchparam.value, searchindex)
  let index;
  for (const items of searchindex) {
    for (const keywords of items.title) {
      const key = keywords.toLowerCase()
      if (searchparam.value.toLowerCase().includes(key)) {
        index = items.index
      }
    }
  }

  if (index) {
    let results = stores[index]
    allStores.value = results
    console.log(allStores.value)
  } else {
    console.log('EMPTY')
  }
}

const toShop = () => {
  const router = useRouter();
  router.go('/zara')
}
</script>

<style scoped lang="less">
#container {
  width: 100%;
}

#search-header {
  width: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
  flex-direction: column;
  margin-top: 50px;

  #search-box {
    width: 80%;
    height: 70px;
    max-width: 600px;
    border-radius: 50px;
    padding: 10px;
    font-size: 1.8rem;
    text-align: center;
    box-shadow: rgba(0, 0, 0, 0.16) 0px 1px 4px;
  }

  #input-group {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-top: 20px;
    gap: 0 15px;
  }

  #search-btn {
    box-sizing: content-box;
    padding: 10px;
    border: 1px solid #cbd5e1;
    background: #fbfffa;
    border-radius: 100%;
    vertical-align: middle;
    cursor: pointer;
    color: #1b4710;
    box-shadow: rgba(0, 0, 0, 0.16) 0px 1px 4px;
  }
}

#search-result {
  margin-top: 20px;
  padding: 20px;
  display: grid;
  grid-template-columns: auto;
  gap: 30px;

  @media @desktop {
    grid-template-columns: auto auto;
  }

  @media @wide {
    grid-template-columns: auto auto auto;
  }

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
}
</style>
