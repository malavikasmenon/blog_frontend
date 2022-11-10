<template>
    <nav class="nav-container">
        <NuxtLink to="/">
            <b-icon-house-door-fill scale="2" variant="dark" class="mx-3"></b-icon-house-door-fill>
        </NuxtLink>
        <NuxtLink to="/new">
            <b-icon-pencil-square scale="2" variant="dark" class="mx-3"></b-icon-pencil-square>
        </NuxtLink>
    </nav>
</template>

<script>
import { BIcon, BIconHouseDoorFill, BIconPencilSquare } from 'bootstrap-vue'
export default {
    components: {
        BIconHouseDoorFill,
        BIconPencilSquare
    }
}
</script>

<style>
.nav-container {
   text-align: right; 
   /* border: 1px solid black; */
   padding: 1%;
}
</style>