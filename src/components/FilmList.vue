<script>
export default {
    name:'FilmList',
    props: ['filmList'],
    methods:{
        changeValue(publicValue) {
            if (publicValue) {
                this.$emit('changeValue', film.public = false)
            }else{
                this.$emit('changeValue', film.public = true)
            }
                
        }
    }
}

</script>

<template>
    <ul>
        <li :class="{off: !film.public}" v-for="film in filmList" :key="film.title">
            {{ film.title }}
            <button v-on:click="() => this.$emit('handlePublic', film)">
                {{ film.public ? 'Private' : 'Public' }}
            </button>

        </li>
    </ul>

</template>

<style scoped>

    li.off{
        background: red;
        color: white;
    }
</style>