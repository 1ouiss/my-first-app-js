<template>
    <div>
        <h1> {{ message }}</h1>
        <FormContact />
    </div>
</template>

<script>
    import FormContact from '../components/FormContact.vue';
    export default {
        name: 'ContactView',
        components: {
            FormContact
        },
        data() {
            return {
                message: 'Contact page'
            }
        }
    }
</script>