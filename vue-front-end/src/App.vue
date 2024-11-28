<template>
  <div id="app">
    <div v-if="notification" class="notification">{{notification}}</div>
    <HeaderApp/>
    <NavApp :categories="categories" :subcategories="subcategories"/>
    <div class="ctn-row">
      <PosterSlide :posters="posters" />
    </div>
    <div class="ctn-row">
      <TopSeller :products="products" />
    </div>
    <div class="ctn-row">
      <CategoryBook :products="products" :poster_skill="poster_skill"/>
    </div>
    <FooterApp/>
    <ChatBox/>
  </div>
</template>

<script>
import HeaderApp from "./components/HeaderApp.vue";
import NavApp from "./components/NavApp.vue";
import PosterSlide from "./components/PosterSlide.vue";
import TopSeller from "./components/TopSeller.vue";
import CategoryBook from "./components/CategoryBook.vue";
import FooterApp from "./components/FooterApp.vue";
import ChatBox from "./components/ChatBox.vue";

export default {
  name: "App",
  components: {
    HeaderApp,
    NavApp,
    PosterSlide,
    TopSeller,
    CategoryBook,
    FooterApp,
    ChatBox,
  },
  data() {
    return {
      notification: "",

      posters: [],
      poster_skill: "",
      poster_family: "",
      poster_science: "",

      products: [],
      products_skill: [],
      products_family: [],
      products_science: [],

      categories: [],
      subcategories: [],
    };
  },
  mounted() {
    // Lấy dữ liệu từ file JSON khi component được mount
    fetch("/DATABASE/data.json")
      .then((response) => response.json()) // Chuyển đổi dữ liệu thành đối tượng JavaScript
      .then((data) => {
        this.notification = data.notification;
        this.posters = data.posters;
        this.products = data.product;
        this.poster_skill = data.poster_skill;
        this.poster_science = data.poster_science;
        this.products_science = data.product_science;
        this.products_family = data.products_family;
        this.poster_family = data.poster_family;

        this.categories = data.categories;
        this.subcategories = data.subcategories;
      })
      .catch((error) => console.error("Có lỗi xảy ra:", error)); // Xử lý lỗi nếu có
  },
};
</script>

<style>
* {
  box-sizing: border-box;
}
#app {
  width: 100%;

  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.ctn-row{
  display: flex;
  flex-direction: column;
  align-items: center;

  margin-bottom: 50px;
}

.notification {
  padding: 3px;
  background-color: rgb(1, 137, 255);

  display: flex;
  justify-content: center;
  
  font-weight: bold;
  font-size: 30px;
  color: rgb(255, 255, 255);
}
</style>
