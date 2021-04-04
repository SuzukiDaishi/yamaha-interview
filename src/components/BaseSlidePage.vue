<template>
    <div class="page">
        <slot />
    </div>
</template>

<script>
    export default {
        name: 'BaseSlidePage'
    }
</script>

<style>
.page {
    width: 100vw;
    height: 100vh;
}
</style>