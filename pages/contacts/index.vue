<script setup>
const ggg = useNuxtApp()

console.log("ggg",ggg);

</script>

<template>
    <div>
        Contacts {{ $route.params }}
    </div>
</template>