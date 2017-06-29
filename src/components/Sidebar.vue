<template>
    <aside class="Hui-aside">
        <ul class="menu_dropdown bk_2">
            <sidebar-item v-for="(item,index) in items" :item="item" :key="item.id"></sidebar-item>
        </ul>
    </aside>
</template>

<script>
import SidebarItem from "./SidebarItem";
export default {
    props: ["items"],
    components:{
        SidebarItem
    },
    computed: {
        data() {
            return data;
        }
    }
}
</script>