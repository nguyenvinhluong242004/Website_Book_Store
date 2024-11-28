<template>
  <div>
    <div class="bottom">
      <div class="header-bottom">
        <div class="new-register">
          <i class="fas fa-envelope"></i>
          <div class="news">ĐĂNG KÍ NHẬN TIN</div>
        </div>
        <div class="input-header-bottom">
          <input
            type="text"
            style="border-radius: 5px; border: none; height: 50%; width: 80%"
            placeholder="Nhập địa chỉ của bạn"
          />
          <button class="btn-bottom">Đăng ký</button>
        </div>
      </div>
      <div class="body-bottom">
        <div class="address">
          <div class="grid-item-logo">
            <i class="fas fa-book"></i>
            <div class="logo">BÁCH KHOA SÁCH</div>
          </div>
          <div class="content-address">
            <div class="infor">
              Lầu 5, 387-389 Hai Bà Trưng Quận 3 TP HCM Công Ty Cổ Phần Phát
              Hành Sách TP HCM - BKS
            </div>
            <div class="infor">
              BKS.com nhận đặt hàng trực tuyến và giao hàng tận nơi.
            </div>
            <div class="infor">
              KHÔNG hỗ trợ đặt mua và nhận hàng trực tiếp tại văn phòng cũng như
              tất cả Hệ Thống Fahasa trên toàn quốc.
            </div>
            <div class="icon-contact">
              <i class="fab fa-facebook"></i>
              <i class="fab fa-instagram"></i>
              <i class="fab fa-youtube"></i>
              <i class="fab fa-tiktok"></i>
              <i class="fab fa-pinterest"></i>
            </div>
            <div class="certificate">
              <i class="fas fa-certificate"></i>
              CHỨNG NHẬN
            </div>
          </div>
        </div>

        <div class="vertical-line"></div>

        <div class="bottom-option">
          <div class="container-bottom-option">
            <div class="service">
              <div class="title">DỊCH VỤ</div>
              <li>Điều khoản và sử dụng</li>
              <li>Chính sách bảo mật</li>
              <li>Chính sách bảo mật thanh toán</li>
              <li>Giới thiệu Bách Khoa Sách</li>
              <li>Liên hệ:</li>
              <div class="contact">
                <i class="fas fa-map-marker-alt"></i>
                <span> 60-62 Lê Lợi, Q.1, TP. HCM</span>
              </div>
            </div>
            <div class="suport">
              <div class="title">HỖ TRỢ</div>
              <li>Chính sách đổi trả hoàn tiền</li>
              <li>Chính sách bảo mật</li>
              <li>Chính sách vận chuyển</li>

              <li>CSKH:</li>
              <div class="care">
                <i class="fas fa-phone"></i>
                <span> cskh@fahasa.com.vn</span>
              </div>
            </div>
            <div class="account">
              <div class="title">TÀI KHOẢN CỦA TÔI</div>
              <li>Đăng nhập/ Tạo mới tài khoản</li>
              <li>Thay đổi địa chỉ khách hàng</li>
              <li>Chi tiết tài khoản</li>
              <li>Lịch sử mua hàng</li>
              <li>SĐT:</li>
              <div class="phone-number">
                <i class="fas fa-mobile-alt"></i>
                <span> 1900636467</span>
              </div>
            </div>
          </div>
          <div class="ship">
            <img src="/IMG/ship.jpg" alt="ship" />
          </div>
        </div>
      </div>
    </div>
    <div class="bottom-text">
      Giấy chứng nhận Đăng ký Kinh doanh số 0304132047 do Sở Kế hoạch và Đầu tư
      Thành phố Hồ Chí Minh cấp ngày 20/12/2005, đăng ký thay đổi lần thứ 10,
      ngày 20/05/2022.
    </div>
  </div>
</template>

<script>
export default {
  name: "FooterApp",
};
</script>

<style scoped>
.bottom {
  background-color: #f4f4f4;
  border-radius: 5px;
}
.header-bottom {
  width: 100%;
  height: 60px;
  border-radius: 5px;
  display: flex;
  justify-content: space-around;
  align-items: center;
  background-color: #959595;
}
.new-register {
  color: white;
  font-size: 30px;
  font-weight: bold;
  width: 400px;
  height: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
}
.input-header-bottom {
  border-radius: 5px;
  width: 500px;
  height: 80%;
  display: flex;
  justify-content: space-around;
  align-items: center;
  background-color: #206484;
}
.btn-bottom {
  height: 50%;
  border: none;
  border-radius: 5px;
  color: red;
  font-weight: bold;
  font-size: 15px;
  background-color: #f5c92b;
}

.body-bottom {
  display: flex;
  justify-content: space-between;
  align-items: center;
  height: 350px;
}
.address {
  position: relative;
  height: 100%;
  width: 40%;
  display: flex;
  flex-direction: column;
}
.grid-item-logo {
  display: flex;
  align-items: center;
  text-align: center;
}
.fa-book {
  font-size: 20px;
  color: rgb(29, 90, 143);
  margin-right: 20px;
}
.logo {
  font-size: 20px;
  font-weight: bold;
  color: rgb(29, 90, 143);
  font-style: italic;
}

.vertical-line {
  width: 2px;
  height: 250px;
  background-color: rgb(151, 151, 151);
  /* Màu sắc */
}

.container-bottom-option {
  width: 100%;
  display: flex;
  justify-content: space-evenly;

  font-size: 15px;
}
.bottom-option {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  align-items: center;
  width: 70%;
}
.title {
  color: #021a2d;
  font-weight: bold;
  font-size: 15px;
}
.content-address {
  color: #205aa2;
  font-weight: bold;
  height: 50%;
  display: flex;
  flex-direction: column;
  justify-content: space-evenly;
}
.icon-contact {
  position: absolute;
  width: 100%;
  font-size: 30px;
  display: flex;
  justify-content: center;
  gap: 20px;
  bottom: 70px;
}
.certificate {
  position: absolute;
  width: 100%;
  font-size: 30px;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 10px;
  bottom: 10px;
}
.ship {
  margin-top: 20px;
}
.ship img {
  width: 100%;
  height: 150px;
}

.bottom-text {
  width: 100%;
  display: flex;
  justify-content: center;
}
</style>