<!--  -->
<template>
  <div id="layout">
    <el-container class="layout-box">
        <el-aside width="200px">
            <div id="logo">
                <img src="../assets/logo.png" alt="">
            </div>
            <v-layout-menu></v-layout-menu>
        </el-aside>
        <el-container>
            <el-header>

            </el-header>
            <el-main>

            </el-main>
        </el-container>
    </el-container>
  </div>
</template>

<script>
import layoutMenu from "@/components/menu"

export default {
  data () {
    return {
    };
  },

  components: {
      "v-layout-menu":layoutMenu
  },

  computed: {},

  methods: {}
}

</script>
<style scoped lang="scss">
#layout,.layout-box{
    width: 100%;
    height: 100%;
}
.el-header{
    background-color: #B3C0D1;
    color: #333;
    text-align: center;
    line-height: 60px;
}
  
.el-aside {
    background-color: #001529;
    color: #333;
    text-align: left;
    height: 100%;
}
  
.el-main {
    background-color: #E9EEF3;
    color: #333;
    text-align: center;
    height: 100%;
}
#logo{
    height: 60px;
    background-color: #002140;
    img{
        width: 80%;
        padding:0 10%;
        position: relative;
        top: 50%;
        transform: translateY(-50%)
    }
}

</style>