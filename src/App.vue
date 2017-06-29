<template>
  <div id="app" class="container">
    <navbar></navbar>
    <sidebar :items="items"></sidebar>
    <router-view></router-view>
  </div>
</template>

<script>
import Navbar from "./components/Navbar";
import Sidebar from "./components/Sidebar";
export default {
  name: 'app',
  components:{
    Navbar,
    Sidebar
  },
  data(){
    return{
      items:[{
        id:"1",
        text:"主页",
        icon:"fa fa-home",
        url:"/"
      },{
        id:"2",
        text:"栏目管理",
        icon:"fa fa-plus",
        url:"/colum"
      },{
        id:"3",
        text:"系统管理",
        icon:"fa fa-settings",
        nodes:[
          {
            id:"3-1",
            text:"数据字典",
            url:"/dictionary"
          },
          {
            id:"3-2",
            text:"系统设置",
            url:"/systemSetting"
          }
        ]
      }]
    }
  }
}
</script>

<style lang="scss">
@import "../static/sass/blog";

.container{
  display: flex;
}
</style>
