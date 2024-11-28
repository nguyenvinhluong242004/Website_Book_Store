<template>
  <div class="nav">
    <div class="nav-product nav-tab" @click="menuClick" @mouseleave="hideMenu">
      <i class="fas fa-bars"></i>
      <div>TẤT CẢ SẢN PHẨM</div>
      <div class="menuBox" v-if="menuVisible">
        <div
          class="menuItem"
          v-for="(item, index) in categories"
          :key="index"
          @mouseover="showSubmenu(index)"
          @mouseleave="hideSubmenu"
        >
          {{ item.name }}
          <div v-if="activeCategory === index" class="submenu">
            <div class="submenuCaption">{{ item.name }}</div>
            <p
              v-for="(subItem, subIndex) in subcategories[index].items"
              :key="subIndex"
            >
              {{ subItem.name }}
            </p>
          </div>
        </div>
      </div>
    </div>
    <div class="nav-intro nav-tab">GIỚI THIỆU</div>
    <div class="nav-news nav-tab">TIN TỨC</div>
    <div class="nav-review nav-tab">REVIEW</div>
    <div class="nav-colab nav-tab">HỢP TÁC</div>
    <div class="nav-lookUp nav-tab">TRA CỨU ĐƠN</div>
  </div>
</template>
  
  <script>
export default {
  name: "NavApp",
  data() {
    return {
      menuVisible: false,
      activeCategory: {},
    };
  },
  props: ["categories", "subcategories"],
  methods: {
    menuClick() {
      if (this.menuVisible === false) {
        // Ẩn hiện menu khi ấn nút
        this.menuVisible = true;
      } else {
        this.menuVisible = false;
      }
    },
    hideMenu() {
      this.menuVisible = false; // Ẩn menu khi rời
    },
    showSubmenu(index) {
      this.activeCategory = index; // Hiện submenu danh mục đang hover
    },
    hideSubmenu() {
      this.activeCategory = null; // ẩn submenu khi rời
    },
  },
};
</script>
  
<style scoped>
.nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  width: 100%;
  height: 50px;
  background-color: #5f7485;
  position: relative;
  margin-bottom: 40px;
}
.nav-tab {
  width: 16.66%;
  height: 100%;
  display: flex;
  justify-content: center;
  align-items: center;

  color: white;
  font-weight: bold;
}
.fa-bars {
  margin-right: 10px;
}

.menuBox {
  position: absolute;
  top: 50px;
  left: 0px;
  background: white;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
  width: 300px;
  z-index: 1000;

  font-weight: normal;
}
.menuItem {
  padding: 8px 12px;
  cursor: pointer;
  /* border-bottom: 1px solid rgb(174, 174, 174); */
  color: black;
}
.menuItem:hover {
  background: rgb(255, 102, 0);
  color: white;
}

/*SubMenu*/
.submenu {
  position: absolute;
  top: 0;
  left: 100%; /* Hiện bên phải của menu */
  background: rgb(240, 239, 239);
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
  padding: 10px;
  width: 300px;
  height: 100%;
  z-index: 1000;
}
.submenu p {
  margin: 5px;
  padding: 5px 10px;
  color: black;
  cursor: pointer;
}
.submenu p:hover {
  color: rgb(255, 89, 0);
}
.submenuCaption {
  padding: 0px 10px;

  color: rgb(255, 89, 0);
  font-size: large;

  cursor: default;
}
</style>