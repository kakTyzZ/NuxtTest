<script setup>
const route = useRoute()

console.log("route",route.params);

</script>

<template>
    <div>
        Prices {{ $route.params }}
    </div>
</template>