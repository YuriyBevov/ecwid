<template>
    <div>
        <Gallery />
        <Features/>
        <Intro />
    </div>
</template>

<script>
    import Gallery from '@/components/Gallery.vue'
    import Features from '@/components/Features.vue'
    import Intro from '@/components/Intro.vue'

    export default {
        name: 'IndexPage',

        components: {
            Gallery,
            Features,
            Intro
        }
    }
</script>