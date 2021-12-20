<template>
    <div>
        <div class="px-3">
            <SelectGenre :genres="genres" @genre="onGenreEvent" />
        </div>
        <div class="d-flex flex-wrap">
            <Disc v-for="(discItem, index) in discsFiltered" :key="index" :disc="discItem"/>
        </div>
    </div>
</template>

<script>
import axios from "axios";
import Disc from "../commons/Disc";
import SelectGenre from "../commons/SelectGenre";

export default {
    name: "AlbumsList",
    components: {
        Disc,
        SelectGenre
    },
    data() {
        return {
            discs: [],
            genreSelected: "",
            genres: []
        };
    },
    created() {
        axios
            .get("https://flynn.boolean.careers/exercises/api/array/music")
            .then((res) => {
                this.discs = res.data.response;

                this.discs.forEach(elm => {
                    if( this.genres.includes(elm.genre) == false ) {
                        this.genres.push(elm.genre);
                    }
                });
            })
            .catch((err) => {
                console.log(err);
            });
    },
    methods: {
        onGenreEvent(payload) {
            this.genreSelected = payload;
        }
    },
    computed: {
        discsFiltered() {
            const discsFiltered = this.discs.filter( (elm) => {
                return elm.genre.includes(this.genreSelected); // return true o false
            } );

            return discsFiltered;
        }
    }
};
</script>

<style>

</style>