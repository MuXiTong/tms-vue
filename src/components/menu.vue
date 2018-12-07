<!-- 菜单列表 -->
<template>
  <div id="layout-menu">
        <el-menu
            default-active="0"
            class="el-menu-vertical-demo"
            background-color="#001529"
            text-color="#fff"
            active-text-color="#ffd04b">
                <!-- 获取一级菜单 -->
                <template v-for="(data,index) in menuData">
                    <!-- 判断一级菜单是否有下级菜单 -->
                    <template v-if="data.group">
                        <el-submenu :key="index" :index="index+''">
                            <template slot="title">
                                <i :class="data.icon"></i>
                                <span class="el-title">{{data.title}}</span>
                            </template>
                            <!-- 获取二级菜单 -->
                            <template v-for="(group,i) in data.group" >
                                <!-- 判断二级菜单是否有下级菜单 -->
                                <template v-if="group.group">
                                    <el-submenu :key="index+'-'+i" :index="index+'-'+i">
                                        <template slot="title">{{group.title}}</template>
                                        <!-- 获取三级菜单 -->
                                        <el-menu-item v-for="(item,j) in group.group" :key="index+'-'+i+'-'+j" :index="index+'-'+i+'-'+j">{{item.title}}</el-menu-item>
                                    </el-submenu>
                                </template>
                                <template v-else>
                                    <el-menu-item :key="index+'-'+i" :index="index+'-'+i">
                                        <span slot="title">{{group.title}}</span>
                                    </el-menu-item>
                                </template>
                            </template>
                        </el-submenu>
                    </template>
                    <template v-else>
                        <el-menu-item :key="index" :index="index+''">
                            <i class="el-icon-setting"></i>
                            <span slot="title">{{data.title}}</span>
                        </el-menu-item>
                    </template>
                </template>
        </el-menu>
  </div>
</template>

<script>

export default {
    name: 'layout-menu',
    data () {
        return {
            menuData:[
                {
                    title:"导航一",
                    icon:"el-icon-location",
                    group:[
                        {
                            title:"分组一",
                            group:[
                                {title:"选项1"},
                                {title:"选项2"},
                            ]
                        },
                        {
                            title:"分组二",
                            group:[
                                {title:"选项3"},
                                {title:"选项4"},
                            ]
                        },
                        {
                            title:"分组三"
                        }
                    ]
                },
                {
                    title:"导航二",
                    icon:"el-icon-location",
                }
            ]
        };
    },

    components: {},

    computed: {},

    methods: {}
}

</script>
<style lang='scss' scoped>
    #layout-menu{
        height: calc(100vh - 60px)
    }
    .el-menu{
        border-right: 0 none;
        .el-title{
            color:#999;
        }
    }
</style>
