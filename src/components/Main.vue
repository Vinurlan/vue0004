<template>
    <div class="content-main">
        <header class="content-main__header">
            <h2 class="text-header">Frontend site</h2>
        </header>
        <nav class="content-main__nav">
            <Navigation @page="changePage"></Navigation>
        </nav>
        <main class="content-main__main">
            <MainContent :currpage="currentPage" :pagesarr="pages"></MainContent>
        </main>
        <footer class="content-main__footer"></footer>
    </div>
</template>

<script>
import Navigation from "./Navigation.vue";
import MainContent from "./MainContent.vue";

export default {
    name: "Main",
    components: {
        Navigation, MainContent
    },
    data() {
        return {
            pages: ["HomePage", "FormsPage", "BasedatPage", "EmptyPage"],
            currentPage: 0,
        }
    },
    methods: {
        changePage(target) {
            this.currentPage = target;
        }
    }


}
</script>

<style lang="scss" scoped>
@import "../assets/styles.scss";

.content-main {
    width: 100%;
    height: 100%;
    margin: 0;
    padding: 100px 0 100px 300px;
    display: block;
    position: relative;
    background-color: $main-color;
}

.content-main__header {
    width: 100%;
    height: 100px;
    background-color: $second-color;
    position: fixed;
    top: 0;
    left: 0;
    display: flex;
    justify-content: center;
    align-items: center; 
    h2 {
        font-size: 20pt;
        
    }
}

.content-main__nav {
    width: 300px;
    height: 100%;
    position: fixed;
    left: 0;
    top: 100px;
    background-color: $second-color;
}

</style>