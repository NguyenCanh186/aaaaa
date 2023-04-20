<template>
  <div>
    <nav
      class="navbar navbar-expand-lg navbar-dark bg-info fixed-top p-st"
    >
      <div class="container">
        <a
          class="navbar-brand"
          href="/"
          @click.prevent="$emit('scroll', 'home')"
        >
          <Logo :nightMode="nightMode" />
        </a>
        <button
          class="navbar-toggler"
          type="button"
          data-toggle="collapse"
          data-target="#navbarSupportedContent"
          aria-controls="navbarSupportedContent"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span style="color: gray; font-size: 23px;"
            ><i class="fas fa-bars"></i>
            </span>
        </button>

        <div class="collapse navbar-collapse" id="navbarSupportedContent">
          <ul class="navbar-nav ml-auto">
            <li class="nav-item mx-2">
              <a
                class="nav-link"
                href="#"
                @click.prevent="$emit('scroll', 'portfolio')"
                :class="{ 'text-light': nightMode }"
                >
                <div class="dropdown">
                  <a href="#" style="text-decoration: none; color: white">Chuyên mục / Thể loại <i class="fa fa-caret-down"></i></a>
                  <div class="dropdown-content">
                    <div class="product">
                      <a href="#">Gói giải trí tổng hợp</a>
                      <div class="dropdown-options">
                        <a href="#" class="option" style="color: white;" >Kho truyện</a>
                        <a href="#" class="option" style="color: white">Âm nhạc</a>
                        <a href="#" class="option" style="color: white">Kinh tế</a>
                        <a href="#" class="option" style="color: white">Tin tức</a>
                      </div>
                    </div>
                    <div class="product">
                      <a href="#">Gói tư vấn chăm sóc sức khỏe</a>
                      <div class="dropdown-options">
                        <a href="#" class="option" style="color: white;" >Giáo dục giới tính</a>
                        <a href="#" class="option" style="color: white">Chàng - Nàng</a>
                        <a href="#" class="option" style="color: white">Sức khỏe</a>
                        <a href="#" class="option" style="color: white">Tâm sự thầm kín</a>
                        <a href="#" class="option" style="color: white">Truyện tình lãng mạn</a>
                      </div>
                    </div>
                  </div>
                </div>
              </a>
            </li>
            <li class="nav-item mx-2">
              <a
                  class="nav-link"
                  href="#"
                  @click.prevent="$emit('scroll', 'portfolio')"
                  :class="{ 'text-light': nightMode }"
              >
                <div class="dropdown">
                  <a href="#" style="text-decoration: none; color: white">Thông tin dịch vụ <i class="fa fa-caret-down"></i></a>
                  <div class="dropdown-content">
                    <div class="product">
                      <a href="#">Thông tin</a>
                    </div>
                    <div class="product">
                      <a href="#">Giới thiệu</a>
                    </div>
                    <div class="product">
                      <a href="#">Hướng dẫn</a>
                    </div>
                    <div class="product">
                      <a href="#">Điều khoản dịch vụ</a>
                    </div>
                  </div>
                </div>
              </a>
            </li>
            <li class="nav-item mx-2">
              <a
                  class="nav-link"
                  href="#"
                  @click.prevent="$emit('scroll', 'portfolio')"
                  :class="{ 'text-light': nightMode }"
              >
                <div class="dropdown">
                  <a href="#" style="text-decoration: none; color: white">Đăng nhập</a>
                </div>
              </a>
            </li>
          </ul>
        </div>
      </div>
    </nav>
  </div>
</template>

<script>
import Logo from "./helpers/Logo";
import info from "../../info";

export default {
  name: "Navbar",
  props: {
    nightMode: {
      type: Boolean,
    },
  },
  data() {
    return {
      navbarConfig: info.config.navbar,
      localNightMode: this.nightMode,
    };
  },
  components: {
    Logo,
  },
  methods: {
    switchMode() {
      this.localNightMode = !this.localNightMode;
      this.$emit("nightMode", this.localNightMode);
    },
  },
};
</script>

<style scoped>
.nav-link {
  color: white;
  font-weight: 500;
}
.nav-link:hover{
}

button {
  border: none;
  outline: none;
}

button:hover {
  border: none;
  outline: none;
}

nav {
  border-bottom: 1px solid rgba(160, 159, 159, 0.336);
  position: fixed !important;
}

.navbar-blur {
  backdrop-filter: blur(12px);
}







.navbar {
  background-color: #333;
  color: #fff;
  display: flex;
  justify-content: space-between;
  padding: 10px;
}

.dropdown {
  position: relative;
}

.dropdown-content {
  background-color: #17a2b8;
  border-radius: 0 0 5px 5px;
  display: none;
  min-width: 160px;
  padding: 10px 0;
  position: absolute;
  right: 0;
  text-align: left;
  top: 100%;
  z-index: 1;
}

.dropdown-content a {
  color: #fff;
  display: block;
  padding: 10px;
  text-decoration: none;
}

.dropdown-content a:hover {
  background-color: #fff;
  color: #17a2b8;
}

.dropdown:hover .dropdown-content {
  display: block;
}

.product {
  display: flex;
  align-items: center;
  position: relative;
  z-index: 2;
}

.product:hover .dropdown-options {
  display: flex;
}

.dropdown-options {
  color: #fff;
  display: none;
  flex-direction: column;
  position: absolute;
  background-color: #17a2b8;
  border-radius: 0 0 5px 5px;
  min-width: 160px;
  padding: 10px 0;
  right: 0;
  text-align: left;
  top: 0;
  left: 100%;
  z-index: 1;
}

.dropdown-options a:hover {
  background-color: #fff;
  color: #17a2b8;
}
.option:hover {
  color: #17a2b8 !important
}











/* Small screens (phones, 600px and below) */
@media only screen and (max-width: 600px) {
  .navbar {
    flex-direction: column;
    align-items: center;
    padding: 10px 0;
  }

  .navbar-blur {
    backdrop-filter: none;
  }

  .dropdown {
    position: static;
  }

  .dropdown-content {

    display: block;
    position: fixed;
    height: 100%;
    width: 100%;
    left: -100%;
    margin-left: 0;
    overflow-y: auto;
    transition: all 0.3s ease;





    background-color: #333;
    min-width: 100%;
    border-radius: 0;
    padding: 10px 0;
    top: initial;
  }

  .dropdown-content a {
    padding: 5px;
    border-bottom: 1px solid rgba(255, 255, 255, 0.2);
  }

  .dropdown:hover .dropdown-content {
    display: none;
  }

  .product {
    margin-top: 10px;
  }

  .product:hover .dropdown-options {
    display: none;
  }

  .dropdown-options {
    position: static;
    display: block;
    background-color: #333;
    min-width: 100%;
    border-radius: 0;
    padding: 10px 0;
    top: initial;
    left: initial;
  }

  .dropdown-options a {
    padding: 5px;
    border-bottom: 1px solid rgba(255, 255, 255, 0.2);
  }

  .option:hover {
    color: #fff !important;
    background-color: #17a2b8;
  }
}

/* Medium screens (tablets, 768px and below) */
@media only screen and (max-width: 768px) {
  .navbar {
    padding: 10px;
  }
}

/* Large screens (desktops, 992px and below) */
@media only screen and (max-width: 992px) {
  /* Add styles here */
}

/* Extra large screens (large desktops, 1200px and below) */
@media only screen and (max-width: 1200px) {
  /* Add styles here */
}




















/* Small screens (phones, 600px and below) */
/*@media screen and (max-width: 1250px){*/
/*  .wrapper nav{*/
/*    max-width: 100%;*/
/*    padding: 0 20px;*/
/*  }*/
/*  nav .content .links{*/
/*    margin-left: 30px;*/
/*  }*/
/*  .content .links li a{*/
/*    padding: 8px 13px;*/
/*  }*/
/*  .wrapper .search-box{*/
/*    max-width: calc(100% - 100px);*/
/*  }*/
/*  .wrapper .search-box input{*/
/*    padding: 0 100px 0 15px;*/
/*  }*/
/*}*/
/*@media screen and (max-width: 900px){*/
/*  nav .content .links{*/
/*    display: block;*/
/*    position: fixed;*/
/*    background: #14181f;*/
/*    height: 100%;*/
/*    width: 100%;*/
/*    top: 70px;*/
/*    left: -100%;*/
/*    margin-left: 0;*/
/*    max-width: 350px;*/
/*    overflow-y: auto;*/
/*    padding-bottom: 100px;*/
/*    transition: all 0.3s ease;*/
/*  }*/
/*  nav #show-menu:checked ~ .content .links{*/
/*    left: 0%;*/
/*  }*/
/*  .content .links li{*/
/*    margin: 15px 20px;*/
/*  }*/
/*  .content .links li a,*/
/*  .content .links li label{*/
/*    line-height: 40px;*/
/*    font-size: 20px;*/
/*    display: block;*/
/*    padding: 8px 18px;*/
/*    cursor: pointer;*/
/*  }*/
/*  .content .links li a.desktop-link{*/
/*    display: none;*/
/*  }*/
/*  !* dropdown responsive code start *!*/
/*  .content .links ul,*/
/*  .content .links ul ul{*/
/*    position: static;*/
/*    opacity: 1;*/
/*    visibility: visible;*/
/*    background: none;*/
/*    max-height: 0px;*/
/*    overflow: hidden;*/
/*  }*/
/*  .content .links #show-features:checked ~ ul,*/
/*  .content .links #show-services:checked ~ ul,*/
/*  .content .links #show-items:checked ~ ul{*/
/*    max-height: 100vh;*/
/*  }*/
/*  .content .links ul li{*/
/*    margin: 7px 20px;*/
/*  }*/
/*  .content .links ul li a{*/
/*    font-size: 18px;*/
/*    line-height: 30px;*/
/*    border-radius: 5px!important;*/
/*  }*/
/*}*/
/*@media screen and (max-width: 400px){*/
/*  .wrapper nav{*/
/*    padding: 0 10px;*/
/*  }*/
/*  .content .logo a{*/
/*    font-size: 27px;*/
/*  }*/
/*  .wrapper .search-box{*/
/*    max-width: calc(100% - 70px);*/
/*  }*/
/*  .wrapper .search-box .go-icon{*/
/*    width: 30px;*/
/*    right: 0;*/
/*  }*/
/*  .wrapper .search-box input{*/
/*    padding-right: 30px;*/
/*  }*/
/*}*/
/*.dummy-text{*/
/*  position: absolute;*/
/*  top: 50%;*/
/*  left: 50%;*/
/*  width: 100%;*/
/*  z-index: -1;*/
/*  padding: 0 20px;*/
/*  text-align: center;*/
/*  transform: translate(-50%, -50%);*/
/*}*/
/*.dummy-text h2{*/
/*  font-size: 45px;*/
/*  margin: 5px 0;*/
/*}*/

</style>
