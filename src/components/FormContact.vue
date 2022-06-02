<template>
    <form @submit.prevent="handleSubmit">
        <input type="text" placeholder="Le titre du film" v-model="credentials.title">
        <input type="text" placeholder="Durée du film" v-model="credentials.duration">
        <input type="text" placeholder="Notation du film" v-model="credentials.notation">
        <input type="submit" value="Envoyer">
    </form>

    <FilmList :filmList="filmList"/>
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
                notation: ''
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
        }
    }

}
</script>