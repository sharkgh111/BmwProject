<template>
                    <div class="model-card">
                            <div class="bmw-img-box">
                                <img :src="model.logo" :alt="model.name" :class="model.class">
                            </div>
                                <div class="info-content">
                                    <div class="heading">
                                        <h4> {{ model.name }} </h4>
                                    </div>
                                        <div class="char-container">
                                            <ul class="char-list">
                                                <li>Power: {{ model.power }}</li>
                                                <li>Engine capacity: {{ model.encapacity }}</li>
                                                <li>Engine type: {{ model.entype }}</li>
                                                <li>Max speed: {{ model.speed }}</li>
                                            </ul>
                                        </div>
                                            <div class="button-block">
                                                <ul class="button-list">
                                                    <li @click="toggleFavorite(model)">
                                                        <svg
                                                         xmlns="http://www.w3.org/2000/svg" 
                                                         width="28" height="28" 
                                                         :fill="model.isFavorite ? 'rgb(255, 0, 0)' : 'white'" 
                                                         viewBox="0 0 16 16"
                                                         :class="{ 'bi bi-suit-heart': !model.isFavorite, 'bi bi-suit-heart-fill': model.isFavorite }"
                                                        >
                                                        <path v-if="model.isFavorite" 
                                                            d="M4 1c2.21 0 4 1.755 4 3.92C8 2.755 9.79 1 12 1s4 1.755 4 3.92c0 3.263-3.234 4.414-7.608 9.608a.513.513 0 0 1-.784 0C3.234 9.334 0 8.183 0 4.92 0 2.755 1.79 1 4 1"
                                                        />
                                                        <path v-else
                                                            d="m8 6.236-.894-1.789c-.222-.443-.607-1.08-1.152-1.595C5.418 2.345 4.776 2 4 2 2.324 2 1 3.326 1 4.92c0 1.211.554 2.066 1.868 3.37.337.334.721.695 1.146 1.093C5.122 10.423 6.5 11.717 8 13.447c1.5-1.73 2.878-3.024 3.986-4.064.425-.398.81-.76 1.146-1.093C14.446 6.986 15 6.131 15 4.92 15 3.326 13.676 2 12 2c-.777 0-1.418.345-1.954.852-.545.515-.93 1.152-1.152 1.595zm.392 8.292a.513.513 0 0 1-.784 0c-1.601-1.902-3.05-3.262-4.243-4.381C1.3 8.208 0 6.989 0 4.92 0 2.755 1.79 1 4 1c1.6 0 2.719 1.05 3.404 2.008.26.365.458.716.596.992a7.6 7.6 0 0 1 .596-.992C9.281 2.049 10.4 1 12 1c2.21 0 4 1.755 4 3.92 0 2.069-1.3 3.288-3.365 5.227-1.193 1.12-2.642 2.48-4.243 4.38z"
                                                        />
                                                        </svg>
                                                    </li>
                                                    <li @click="toggleBookmarks(model)">
                                                        <svg 
                                                          :class="model.isBookmarked ? 'bi bi-bookmark-check' : 'bi bi-bookmark-plus'"
                                                          :style="{ filter: model.isBookmarked ? 'drop-shadow(0 0 25px rgb(225, 255, 100))' : 'none' }"
                                                          xmlns="http://www.w3.org/2000/svg" 
                                                          width="28" height="28" 
                                                          :fill="model.isBookmarked ? 'rgb(255, 255, 0)' : '#fff'" 
                                                          viewBox="0 0 16 16"
                                                        >
                                                            <path
                                                                v-if="model.isBookmarked"
                                                                fill-rule="evenodd" d="M2 15.5V2a2 2 0 0 1 2-2h8a2 2 0 0 1 2 2v13.5a.5.5 0 0 1-.74.439L8 13.069l-5.26 2.87A.5.5 0 0 1 2 15.5m8.854-9.646a.5.5 0 0 0-.708-.708L7.5 7.793 6.354 6.646a.5.5 0 1 0-.708.708l1.5 1.5a.5.5 0 0 0 .708 0z"
                                                                />
                                                            <path
                                                                v-else
                                                                fill-rule="evenodd" d="M2 15.5V2a2 2 0 0 1 2-2h8a2 2 0 0 1 2 2v13.5a.5.5 0 0 1-.74.439L8 13.069l-5.26 2.87A.5.5 0 0 1 2 15.5m6.5-11a.5.5 0 0 0-1 0V6H6a.5.5 0 0 0 0 1h1.5v1.5a.5.5 0 0 0 1 0V7H10a.5.5 0 0 0 0-1H8.5z"
                                                            />
                                                            <path d="M2 2a2 2 0 0 1 2-2h8a2 2 0 0 1 2 2v13.5a.5.5 0 0 1-.777.416L8 13.101l-5.223 2.815A.5.5 0 0 1 2 15.5zm2-1a1 1 0 0 0-1 1v12.566l4.723-2.482a.5.5 0 0 1 .554 0L13 14.566V2a1 1 0 0 0-1-1z" />
                                                        </svg>
                                                    </li>
                                                </ul>
                                            </div>
                                </div>
                        </div>
</template>

<style scoped>

   .model-card {
        width: 95%;
        height: 80px;
        border: 1px solid #cccccc6b;
        background: linear-gradient(140deg, rgb(33, 72, 151) 60%, rgb(88, 123, 192) 100%);
        box-shadow: 2px 5px 15px #000000a8;
        border-radius: 15px;
        padding: 0 15px;
        display: flex;
        transition: all 0.2s ease;
        overflow: hidden;
    }

    .model-card:hover {
        transform: scale(1.03);
        cursor: pointer;
        box-shadow: 2px 2px 20px #000000;
        filter: brightness(120%);
    }

    .model-card:active {
        transform: translateY(3px) scale(1.03);
    }

    .bmw-img-box{
        max-width: 140px;
        max-height: 160px;
        display: flex;
        align-items: center;
        margin-right: 20px;
        overflow: hidden;
        box-sizing: border-box;
    }

    .model-card img {
        position: relative;
        width: 100%;
        height: 130%;
        object-fit: cover;
        transform: translate(5px, -5px);
        margin: 0 auto;
    }

     .info-content {
        display: flex;
        align-items: center;
        width: 100%;
    }

    .info-content .heading {
        display: block;
        padding: 0 5px;
        align-content: center;
        border-left: 1px solid #c0cbff5c;
        border-right: 1px solid #c0cbff5c;
        min-width: 180px;
        height: 85px;
    }

    .info-content .heading h4 {
        font-size: 18px;
        font-style: italic;
        text-align: center;
        color: rgb(255, 255, 255);
        line-height: 22px;
    }

    .info-content .char-container {
        border-right: 1px solid #c0cbff5c;
        height: 100%;
        min-width: 380px;
        display: block;
        align-content: center;
        padding: 0 10px;
    }

    .info-content .char-list {
        list-style-type: none;
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        gap: 10px;
    }

    .info-content .char-list li {
        color: rgb(163, 163, 163);
        font-size: 13px;
        font-style: italic;
        font-weight: 600;
        text-align: center;
        display: block;
        align-content: center;
    }

    .info-content .button-block {
        display: flex;
        margin: 0 20px;
        align-items: center;
        height: 100%;
        width: 50%;
    }

    .info-content .button-block ul {
        list-style-type: none;
        display: flex;
        align-items: center;
        justify-content: flex-end;
        gap: 25px;
        width: 100%;
    }

    @media (max-width: 1330px) {
        .model-card {
            height: 320px;
            width: 80%;
            padding: 0;
            padding-bottom: 10px;
            flex-direction: column;
        }
        .info-content {
            flex-direction: column;
            border: none;
        }
        .bmw-img-box {
            margin: 0;
            height: 100%;
            max-width: 100%;
        }
        .info-content .heading {
            border: none;
            border-bottom: 1px solid #ccc;
            width: 100%;
            padding: 5px 0;
        }
        .info-content .char-container {
            min-width: 100%;
            padding:5px;
            border: none;
        }
        .info-content .button-block {
            width: 100%;
            margin: 0;

        }
        .info-content .button-block ul {
            justify-content: space-evenly;
            align-items: center;
        }
        .button-block ul li svg {
            width: 36px;
            height: 36px;
        }
    }
    @media (max-width: 950px) {
        .model-card {
            height: 300px;
            width: 60%;
            padding: 0;
            padding-bottom: 10px;
            flex-direction: column;
        }
        .bmw-img-box {
            max-width: 80%;
        }
    }

</style>

<script>
export default {
    name: 'Card',
    props: {
        model: {
            type: Object,
            required: true
        }
    },
    methods: {
       toggleBookmarks(model) {
        this.$emit('bookmarks-clicked', model)
       },
       toggleFavorite(model) {
        this.$emit('favorites-clicked', model)
       }
   }
}
</script>