<template>
  <div class="top-seller-container">
    <div class="top-seller-label">
      <i class="fas fa-trophy"></i>
      <div>SÁCH BÁN CHẠY</div>
    </div>

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
  name: "TopSeller",
  components: {
    ProductCard,
  },
  props: ["products"],
};
</script>

<style scoped>
.top-seller-container {
  width: 1000px;
  height: 510px;
  background-color: #dfdfdf;
  border-radius: 15px;
  overflow: auto;
}
.top-seller-label {
  width: 200px;
  height: 35px;
  display: flex;
  justify-content: space-evenly;
  align-items: center;
  background-color: #accfe6;
  color: #205aa2;
  border-bottom-right-radius: 10px;
  font-weight: bold;
}
.book-list-container {
  width: 100%;
  height: 450px;
  margin-top: 10px;
  display: flex;
  justify-content: space-evenly;
}
</style>