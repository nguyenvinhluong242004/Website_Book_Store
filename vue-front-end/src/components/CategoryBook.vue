<template>
  <div class="category-book-container">
    <div class="category-book-header">
      <div class="skill-book-tab tab choosen-tab">SÁCH TƯ DUY - KỸ NĂNG</div>
      <div class="family-book-tab tab">TỦ SÁCH - GIA ĐÌNH</div>
      <div class="science-book-tab tab">KHOA HỌC - GIÁO DỤC</div>
      <div class="literature-book-tab tab">VĂN HỌC</div>
    </div>

    <img :src="poster_skill" width="100%" alt="poster" />

    <div class="book-list-container">
      <ProductCard
        v-for="(product, index) in products"
        :key="index"
        :img="product.img"
        :name="product.name"
        :old_price="product.old_price"
        :new_price="product.new_price"
        :type_money="product.type_money"
      />
    </div>
  </div>
</template>
  
<script>
import ProductCard from "./ProductCard.vue";

export default {
  name: "CategoryBook",
  components: {
    ProductCard,
  },
  props: ["products", "poster_skill"],
};
</script>
  
<style scoped>
.category-book-container {
  width: 1000px;
  padding-bottom: 15px;
  background-color: #dfdfdf;
  border-radius: 15px;
  overflow: auto;
}
.category-book-header {
  width: 100%;
  height: 40px;
  background-color: #5f7485;

  display: flex;
  justify-content: space-evenly;
  align-items: center;

  font-weight: bold;
  color: white;
}
.tab{
  width: 25%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;
}
.choosen-tab{
  background:rgb(255, 102, 0);
}
.book-list-container {
  width: 100%;
  height: 450px;
  margin-top: 10px;
  display: flex;
  justify-content: space-evenly;
}
</style>