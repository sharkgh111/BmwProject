<template>
    <div class="main-catalog-content" >
        <div class="select-model-block">
            <div v-if="selectedSeria" class="heading">
                <h3>Select series model "{{ selectedSeria }}"</h3>
            </div>
            <div class="main-bmw-content">
                <ul v-if="selectedSeria" class="card-list">
                        <Card 
                            v-for="model in models[selectedSeria]" 
                            :key="model.name" 
                            :model="model"
                            @bookmarks-clicked="bookmarksClick"
                            @favorites-clicked="favoritesClick"
                        />
                </ul>
                <p v-else>Here will be the result of the selected model</p>
            </div>
        </div>
    </div>
</template>

<style scoped>

    .main-catalog-content {
        font-family: 'Roboto', sans-serif;
        width: 100%;
        height: 450px;
    }

    .select-model-block {
        height: 100%;
        border-radius: 10px;
        background-color: rgba(49, 74, 150, 0.372);
        box-shadow: inset 0 0 5px #000;
        overflow-y: scroll;
        position: relative;
        display: block;
        align-content: center;
        z-index: 10;
    }

    .main-bmw-content {
        margin: 0 40px;
    }

    .select-model-block p {
        text-align: center;
        font-size: 16px;
        font-weight: 500;
        color: rgb(104, 120, 172);
        line-height: 23px;
    }

    .select-model-block .heading {
        position: sticky;
        top: 20px;
        z-index: 100;
        padding: 15px;
        border-top: 1px solid #adadadce;
        border-bottom: 1px solid #adadadce;
        background: rgba(31, 58, 145, 0.736);
        margin: 35px 0;
    }

    .select-model-block .heading h3 {
        position: relative;
        z-index: 150;        
        text-align: center;
        color: aliceblue;
        letter-spacing: 1.2px;
        font-style: italic;
    }

    .select-model-block .card-list {
        list-style-type: none;
        display: flex;
        flex-direction: column;
        align-items: center;
        padding: 10px;
        margin: 15px 0;
        gap: 20px;
    }

    @media (max-width: 1330px) {
        .select-model-block .card-list {
           display: grid;
           grid-template-columns: repeat(3, 2fr);
           place-items: center;
           place-content: center;
           gap: 20px;
        }
        .main-catalog-content {
            margin: 20px 0;
        }
    }
    @media (max-width: 950px) {
        .select-model-block .card-list {
           grid-template-columns: repeat(1, 1fr);
           gap: 40px;
        }
    }

</style>

<script>
import Card from './Card.vue';

export default {
   name: 'MainCatalogBlock',
   components: { Card },
   props: ['selectedSeria', 'models', 'model'],
   methods: {
    bookmarksClick(model) {
        this.$emit('add-to-bookmarks', model)
    },
    favoritesClick(model) {
        this.$emit('add-to-favorites', model)
    }
   }
}
</script>