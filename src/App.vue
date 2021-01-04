<template>
    <dir>
        <the-header title="RememberMe"></the-header>
        <the-resources></the-resources>
    </dir>
</template>

<script>
import TheHeader from './components/layouts/TheHeader.vue';
import TheResources from './components/learning-resources/TheResources.vue';

    export default {
        components: {
            TheHeader,
            TheResources
        },
    }
</script>

<style>
    * {
        box-sizing: border-box;
    }
</style>