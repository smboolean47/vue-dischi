<template>
    <main class="container mt-5">
        <AlbumsList/>
    </main>
</template>

<script>
import AlbumsList from '../sections/AlbumsList.vue';

export default {
    name: "Main",
    components: {
        AlbumsList
    }
}
</script>