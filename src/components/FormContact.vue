<template>
    <form @submit.prevent="handleSubmit">
        <input type="text" placeholder="Le titre du film" v-model="credentials.title">
        <input type="text" placeholder="Durée du film" v-model="credentials.duration">
        <input type="text" placeholder="Notation du film" v-model="credentials.notation">
        <div>
            <label for="public-on">Public On</label>
            <input id="public-on" type="radio" v-model="credentials.public" value="true">
            <label for="public-off">Public Off</label>
            <input id="public-off" type="radio" v-model="credentials.public" value="false">
        </div>
        <input type="submit" value="Envoyer">
    </form>

    <FilmList :filmList="filmList" v-on:handlePublic="handlePublic"/>
</template>


<script>
import FilmList from '@/components/FilmList.vue'
export default {
    name: 'FormContact',
    components: {
        FilmList
    },
    data() {
        return {
            credentials: {
                title: '',
                duration: '',
                notation: '',
                public: false
            },
            filmList: []
        }
    },
    methods: {
        handleSubmit() {
            this.filmList.push(this.credentials)
            this.credentials = {
                title: '',
                duration: '',
                notation: ''
            }
            console.log(this.filmList);
        },
        handlePublic(film){
            film.public = !film.public
        }
    }
}
</script>