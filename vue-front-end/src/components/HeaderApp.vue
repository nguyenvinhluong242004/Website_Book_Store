<template>
  <div class="header">
    <div class="grid-item-logo">
      <i class="fas fa-book"></i>
      <div class="logo">BÁCH KHOA SÁCH</div>
    </div>
    <div class="grid-item-search">
      <input
        class="input"
        type="text"
        id="myInput"
        name="myInput"
        placeholder="Bạn muốn đọc sách gì..."
      />
      <div class="glass"><i class="fas fa-search"></i></div>
    </div>
    <div class="grid-item-icon">
      <div class="iconNoti">
        <i class="fas fa-bell" @click="notiClick"></i>
        <div v-if="notiVisible" class="notiBox">
          <div class="notiBoxHeader">
            <div>Thông báo</div>
            <div class="notiBoxTxtAllNoti">Xem tất cả</div>
          </div>
          <div class="notiItem">
            <div class="notiItemTitle">Thông báo số 1</div>
            <div class="notiItemContent">hello Thong báo đây lo</div>
          </div>
          <div class="notiItem">
            <div class="notiItemTitle">Thông báo số 2</div>
            <div class="notiItemContent">
              hello Thong báo số 2 đây ai không muốn học thì đi về, không làm
              thì ngủ aaaaaaaaaaaa về nhà... mà cãi nhaoaaaaaaaaa
              aaaaaaaaaaaaaaaaaaaaaaaaaaaaaaa aaa
            </div>
          </div>
          <div class="notiItem">
            <div class="notiItemTitle">Thông báo nghỉ học</div>
            <div class="notiItemContent">hello cả nhà yêu của kem</div>
          </div>
          <div class="notiItem">
            <div class="notiItemTitle">Bạn có một tin nhắn chưa đọc</div>
            <div class="notiItemContent">hello Thong báo đây lo</div>
          </div>
        </div>
      </div>
      <div class="iconCart">
        <i class="fas fa-shopping-cart"></i>
      </div>
      <div class="iconUser">
        <i class="fas fa-user" @click="userClick"></i>
        <div v-if="userVisible" class="userBox">
          <div class="userBoxHeader">
            <div class="userInfor">
              <div class="userAvatar"></div>
              <div class="userName">User Nêm</div>
            </div>
            <i class="fa-solid fa-angle-right"></i>
          </div>
          <div class="userItem" id="myOrder">
            <i class="fa-solid fa-file-invoice-dollar"></i>Đơn hàng của tôi
          </div>
          <div class="userItem" id="favoriteProduct">
            <i class="fa-regular fa-heart"></i>Sản phẩm yêu thích
          </div>
          <div class="userItem" id="logOut">
            <i class="fa-solid fa-arrow-right-from-bracket"></i>Đăng xuất
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "HeaderApp",
  data() {
    return {
      notiVisible: false,
      userVisible: false,
    };
  },
  methods: {
    notiClick() {
      // Ẩn hiện thông báo khi ấn nút
      if (this.notiVisible === false) {
        this.notiVisible = true;
      } else {
        this.notiVisible = false;
      }
      this.userVisible = false;
    },
    userClick() {
      if (this.userVisible === false) {
        this.userVisible = true;
      } else {
        this.userVisible = false;
      }
      this.notiVisible = false;
    },
  },
};
</script>

<style scoped>
.header {
  height: 60px;
  width: 100%;
  background-color: #ffffff;
  padding-left: 20px;
  padding-right: 20px;
  display: grid;
  grid-template-columns: 30% 58% 12%;
}

.grid-item-logo {
  display: flex;
  align-items: center;
  text-align: center;
}
.fa-book {
  font-size: 30px;
  color: rgb(29, 90, 143);
  margin-right: 20px;
}
.logo {
  font-size: 30px;
  font-weight: bold;
  color: rgb(29, 90, 143);
  font-style: italic;
}

.grid-item-search {
  justify-content: start;
  display: flex;
  align-items: center;
  text-align: center;
  padding-left: 40px;
}
.input {
  width: 70%;
  height: 60%;
  padding-left: 10px;
  padding-right: 10px;
  margin-right: 20px;
  color: rgb(29, 90, 143);
  font-style: italic;
  border-radius: 5px;
  border: 1px solid rgb(29, 90, 143);
}
.glass {
  border-radius: 5px;
  display: flex;
  justify-content: center;
  align-items: center;
  width: 38px;
  height: 60%;
  color: rgb(0, 0, 0);
  background-color: rgb(105, 162, 211);
  margin-left: 5px;
  font-size: 22px;
}

.grid-item-icon {
  display: flex;
  justify-content: end;
  text-align: center;
  padding-right: 20px;
}
.grid-item-icon .fas{
  font-size: 21px;
}
.iconNoti {
  width: 50px;
  color: rgb(10, 57, 98);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  position: relative;
}
.notiBox {
  max-height: 350px;
  position: absolute;
  top: 64px;
  right: 0px;
  background: white;
  border-radius: 10px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
  width: 400px;
  z-index: 1001;
  overflow: auto;
  color: rgb(75, 75, 75);
}
.notiBoxHeader {
  width: 100%;
  height: 50px;
  padding: 0px 20px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);

  display: flex;
  justify-content: space-between;
  align-items: center;

  font-weight: bold;
}
.notiBoxTxtAllNoti {
  color: #2e85ff;
}
.notiItem {
  width: 100%;
  height: 100px;
  padding: 15px 20px;
  overflow: hidden;

  text-align: left;
}
.notiItemTitle {
  color: #404040;
  font-weight: bold;
}

.iconCart {
  width: 50px;
  color: rgb(10, 57, 98);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
}

.iconUser {
  width: 50px;
  color: rgb(10, 57, 98);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;

  position: relative;
}
.userBox {
  position: absolute;
  top: 64px;
  right: 0px;
  background: white;
  border-radius: 10px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
  width: 300px;
  z-index: 1001;
  color: rgb(145, 145, 145);
}
.userBoxHeader {
  width: 100%;
  height: 60px;
  padding: 0px 20px;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);

  display: flex;
  justify-content: space-between;
  align-items: center;

  font-weight: bold;
}
.userInfor {
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.userAvatar {
  width: 40px;
  height: 40px;
  border-radius: 100px;
  background: red;

  margin-right: 20px;
}
.userName {
  color: rgb(75, 75, 75);
}
.userItem {
  width: 100%;
  height: 40px;
  padding: 0px 20px;

  display: flex;
  align-items: center;

  text-align: left;
}
.userItem i {
  margin-right: 20px;
}
</style>