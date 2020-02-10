<template>
    <div>
        <ul class="nav-ul">
            <li class="nav-ul__li nav-active"><a href="#" @click="selectPage">Home</a></li>
            <li class="nav-ul__li"><a href="#" @click="selectPage">Forms</a></li>
            <li class="nav-ul__li"><a href="#" @click="selectPage">BaseDat</a></li>
            <li class="nav-ul__li"><a href="#" @click="selectPage">Empty</a></li>
        </ul>
    </div>
</template>

<script>
export default {
    name: "Navigation",
    data() {
        return {
            navActive: 0,
        }
    },
    methods: {
        selectPage(event) {
            let liArr = Object.values(document.getElementsByClassName("nav-ul__li"));
            let liActive = document.querySelector(".nav-active");
            let liTargetLink = event.target.closest("li");

            if (liTargetLink != liActive) {
                liTargetLink.classList.add("nav-active");
                liActive.classList.remove("nav-active");    
                
                let targetId = liArr.findIndex((item) => item === liTargetLink);
                this.$emit("page", targetId);
            }            
        }
    }
}
</script>

<style lang="scss" scoped>
@import "../assets/styles.scss";

ul {
    margin: 0;
    padding: 0;
    text-align: center;
    font-size: 24pt;
    li {
        padding: 0;
        padding-left: 10px;
        background-color: $main-color-dart;
        transition: background-color 0.3s;
    }

    a {
        text-decoration: none;
        color: $text-color-main;
    }
}

.nav-active {
    background-color: $main-color;
}


</style>