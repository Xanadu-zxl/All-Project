<template>
  <div class="home">
    <div class="baner">
      <img v-if="show" class="baner-img" src="@/assets/img/banner-iPad.png" alt="" />
      <img v-else class="baner-img" src="@/assets/img/banner.png" alt="" />
    </div>
    <div class="main">
      <div class="navs">
        <router-link class="inventory" to="/inventory">资产盘点</router-link>
        <router-link class="warning" to="/warning">资产预警</router-link>
      </div>
      <router-view></router-view>
    </div>
  </div>
</template>
<script scoped>
export default {
  data() {
    return {
      screenWidth: document.body.clientWidth,
      show: false,
    }
  },
  methods: {
    showIpad() {
      this.screenWidth > 767 ? (this.show = true) : (this.show = false)
    },
  },
  mounted() {
    this.showIpad()
  },
}
</script>
<style lang="scss" scoped>
.home {
  .baner-img {
    width: 100%;
  }

  .main {
    background: linear-gradient(180deg, #ffffff 0%, #fdfeff 20.31%, #f4f4f8 40.1%, #f4f4f8 100%);
    border-radius: 12px 12px 0px 0px;
    margin-top: -40px;
    padding: 28px 0 0 0;
    position: relative;
    padding: 16px;
  }
  .navs {
    padding: 4px;
    margin-bottom: 27px;
    background: #f4f4f8;
    border-radius: 8px;
    @include dcc;

    .inventory,
    .warning {
      width: 50%;
      height: 30px;
      border-radius: 4px;
      font-size: 14px;
      line-height: 30px;
      text-align: center;
      color: #6b7885;
    }
    .router-link-exact-active {
      background: $pdgtColor;
      color: #fff;
    }
  }
}
</style>
