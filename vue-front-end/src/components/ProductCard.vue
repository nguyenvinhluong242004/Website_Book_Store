<template>
  <div class="product-card">
    <img :src="img" :alt="name" class="product-image" />
    <div class="product-title">{{ name }}</div>
    <div class="product-new-price-info">
      <span class="new-price">{{ formattedNewPrice }} {{ type_money }}</span>
      <span class="discount-tag">-{{ discountPercentage }}%</span>
    </div>
    <div class="old-price">{{ formattedOldPrice }} {{ type_money }}</div>
  </div>
</template>

<script>
export default {
  name: "ProductCard",
  props: ["img", "name", "old_price", "new_price", "type_money"],
  computed: {
    formattedOldPrice() {
      // Đảm bảo rằng giá là một chuỗi hoặc số hợp lệ trước khi định dạng
      let formattedPrice = parseFloat(this.old_price)
        .toString()
        .replace(/\B(?=(\d{3})+(?!\d))/g, ".");
      return formattedPrice; // Trả về giá đã được định dạng
    },
    // Định dạng giá mới trực tiếp trong computed
    formattedNewPrice() {
      let formattedPrice = parseFloat(this.new_price)
        .toString()
        .replace(/\B(?=(\d{3})+(?!\d))/g, ".");
      return formattedPrice; // Trả về giá đã được định dạng
    },
    // Tính toán phần trăm giảm giá
    discountPercentage() {
      let discount = ((this.old_price - this.new_price) / this.old_price) * 100;
      return discount.toFixed(0);
    },
  },
};
</script>

<style scoped>
.product-card {
  height: 450px;
  width: 23%;
  background-color: #ffffff;
  border-radius: 15px;
  text-align: center;
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.1);
  overflow: auto;
}
.product-image {
  width: 100%;
  height: 300px;
}
.product-title {
  height: 85px;
  padding: 10px;
  padding-left: 20px;
  text-align: start;
  font-size: 1.2rem;
}
.product-new-price-info {
  width: 100%;
  height: 25px;
  padding-left: 20px;

  display: flex;
  align-items: center;
}
.new-price {
  color: red;
  font-size: 20px;
  margin-right: 20px;
}
.discount-tag {
  width: 50px;
  height: 30px;
  background-color: rgb(212, 0, 0);

  display: flex;
  justify-content: center;
  align-items: center;

  color: white;
  font-weight: bold;
  font-size: 14px;
  border-radius: 5px;
}
.old-price {
  text-decoration: line-through;
  color: #b5b5b5;
  width: 100%;
  padding-left: 22px;

  display: flex;
  align-items: center;
}
</style>