<template>
    <div>
        <div :is="currentPage"></div>
    </div>
</template>

<script>
import HomePage from "./main-content/HomePage.vue";
import FormsPage from "./main-content/FormsPage.vue";
import BasedatPage from "./main-content/BasedatPage.vue";
import EmptyPage from "./main-content/EmptyPage.vue";

export default {
    name: "MainContent",
    components: {
        HomePage, FormsPage,
        BasedatPage, EmptyPage,
    },
    props: {
        currpage: Number,
        pagesarr: Array,
    },
    data() {
        return {
            pages: [],
            currentPage: "HomePage",
        }
    },
    watch: {
        currpage() {
            this.currentPage = this.pages[this.currpage];
        }
    },
    mounted() {
        this.pages = this.pagesarr;    
    }
}
</script>

<style lang="scss" scoped>



</style>