<script>
export default {
    name:'FilmList',
    props: ['filmList']
}

</script>

<template>
    <ul>
        <li v-for="film in filmList" :key="film.title">
            {{ film.title }}
        </li>
    </ul>

</template>