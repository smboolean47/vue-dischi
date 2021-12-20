<template>
    <select @change="$emit('genre', selectVal)" v-model="selectVal" class="form-select w-auto">
        <option value="">Seleziona un genere</option>
        <option v-for="(genre, index) in genres" :value="genre" :key="index">{{genre}}</option>
    </select>
</template>

<script>
export default {
    name: "SelectGenre",
    data() {
        return {
            selectVal: "",
        }
    },
    props: {
        genres: Array
    }
}
</script>

<style>

</style>