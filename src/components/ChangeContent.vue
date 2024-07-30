<template>
    <component :is="currentPage"/>
</template>

<script>

import Home from './MainContent.vue';
import Catalog from './componentsCatalog/ContentCatalog.vue';
import About from './ContentAbout.vue';

export default {
    components: {
        Home,
        Catalog,
        About
    },
    props: {
        currentPage: {
            type: String,
            required: true
        }
    }
}
</script>