<template>
  <div>
    <div v-if="notification" class="notification">{{ notification }}</div>
    <HeaderApp />
    <NavApp :categories="categories" :subcategories="subcategories" />
    <div class="ctn-row">
      <PosterSlide :posters="posters" />
    </div>
    <div class="ctn-row">
      <TopSeller :products_top="products_top" />
    </div>
    <div class="ctn-row">
      <CategoryBook
        :products_skill="products_skill"
        :poster_skill="poster_skill"
        :products_family="products_family"
        :poster_family="poster_family"
        :products_science="products_science"  
        :poster_science="poster_science"
        :products_literature="products_literature"  
        :poster_literature="poster_literature"

      />
    </div>
    <FooterApp />
    <ChatBox />
  </div>
</template>

<script>
import "./app-css/app.css"; // Import file CSS vào App.vue

import HeaderApp from "./components/vue-component/HeaderApp.vue";
import NavApp from "./components/vue-component/NavApp.vue";
import PosterSlide from "./components/vue-component/PosterSlide.vue";
import TopSeller from "./components/vue-component/TopSeller.vue";
import CategoryBook from "./components/vue-component/CategoryBook.vue";
import FooterApp from "./components/vue-component/FooterApp.vue";
import ChatBox from "./components/vue-component/ChatBox.vue";

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
      poster_literature: "",

      products_top: [],
      products_skill: [],
      products_family: [],
      products_science: [],
      products_literature: [],

      categories: [],
      subcategories: [],
    };
  },
  mounted() {
    // Lấy dữ liệu từ file JSON khi component được mount
    fetch("/DATABASE/data.json")
      .then((response) => response.json()) // Chuyển đổi dữ liệu thành đối tượng JavaScript
      .then((data) => {
        console.log("Dữ liệu nhận được:", data);

        this.notification = data.notification;
        this.posters = data.posters;
        this.products_top = data.products_top;
        this.products_skill = data.products_skill;
        this.poster_skill = data.poster_skill;
        this.poster_science = data.poster_science;
        this.products_science = data.products_science;
        this.products_family = data.products_family;
        this.products_literature = data.products_literature;
        this.poster_family = data.poster_family;
        this.poster_literature = data.poster_literature;
        console.log("top:",this.products_family);
        this.categories = data.categories;
        this.subcategories = data.subcategories;
      })
      .catch((error) => console.error("Có lỗi xảy ra:", error)); // Xử lý lỗi nếu có

     
  },
};
</script>
