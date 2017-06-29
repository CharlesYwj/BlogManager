<template>
    <li>
        <a @click="toggleChild(item)" :class="{acitve:item.childShow}" v-if="item.hasNodes">
            <i :class="item.icon"></i> {{item.text}}
        </a>
        <router-link :to="item.url" v-else>
            <i :class="item.icon"></i> {{item.text}}
        </router-link>
        <ul v-if="item.hasNodes" v-show="item.childShow">
            <li v-for="(child,index) in item.nodes" :child="child" :key="child.id">
                <router-link :to="child.url">{{child.text}}</router-link>
            </li>
        </ul>
    </li>
</template>

<script>
export default {
    props: ["item"],
    created() {
        if (this.item.nodes && this.item.nodes.length > 0) {
            this.$set(this.item, "hasNodes", true);
            this.$set(this.item, "childShow", false);
        } else {
            this.$set(this.item, "hasNodes", false);
        }
    },
    methods: {
        toggleChild() {
            if (this.item.nodes && this.item.nodes.length > 0) {
                this.item.childShow = !this.item.childShow;
            }
        }
    }
}
</script>
