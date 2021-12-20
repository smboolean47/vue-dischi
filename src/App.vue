<template>
    <div id="app">
        <Header/>

        <Main/>
    </div>
</template>

<script>
import Header from "./components/macro/Header";
import Main from "./components/macro/Main";

export default {
    name: "App",
    components: {
        Header,
        Main,
    }
};
</script>

<style lang="scss">
@import "./assets/styles/general";
</style>
