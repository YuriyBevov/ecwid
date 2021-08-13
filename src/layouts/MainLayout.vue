<template>
    <div class="main-container cmn">
        <Header/>
        <Main/>
        <Footer/>
    </div>
</template>

<script>
    import Header from '@/components/Header.vue'
    import Main from '@/components/Main.vue'
    import Footer from '@/components/Footer.vue'

    export default {
        name: 'MainLayout',

        components: {
            Header,
            Footer,
            Main
        }
    }
</script>

<style lang="scss">

</style>