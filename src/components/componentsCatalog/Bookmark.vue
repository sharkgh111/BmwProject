<template>
    <div class="bookmark-content">
        <div class="heading">
            <h2 class="header">Bookmarks</h2>
                <div class="qnt-cards">
                    Num of cards: {{ numCards }}
                </div>
        </div>
        <div class="bookmarks-list-content">
            <ul v-if="bookmarks.length > 0" class="bookmarks-list">
                <li v-for="bookmark in bookmarks" :key="bookmark.name" class="model">
                            <div class="bmw-img-box">
                                <img :src="bookmark.logo" :alt="bookmark.name" :class="bookmark.class">
                            </div>
                                <div class="info-content">
                                    <div class="info-heading">
                                        <h4> {{ bookmark.name }} </h4>
                                    </div>
                                        <div class="char-container">
                                            <ul class="char-list">
                                                <li>Power: {{ bookmark.power }}</li>
                                                <li>Engine capacity: {{ bookmark.encapacity }}</li>
                                                <li>Engine type: {{ bookmark.entype }}</li>
                                                <li>Max speed: {{ bookmark.speed }}</li>
                                            </ul>
                                        </div>
                                </div>
                            <div class="fav-block">
                                <div class="fav-icon-content" title="Favorite">
                                    <svg v-if="bookmark.isFavorite" xmlns="http://www.w3.org/2000/svg" width="28" height="28" fill="rgb(255, 0, 40)" viewBox="0 0 16 16" class="bi bi-suit-heart" style="filter: drop-shadow(0 0 15px rgba(255, 0, 0, 0.769));">
                                        <path d="M4 1c2.21 0 4 1.755 4 3.92C8 2.755 9.79 1 12 1s4 1.755 4 3.92c0 3.263-3.234 4.414-7.608 9.608a.513.513 0 0 1-.784 0C3.234 9.334 0 8.183 0 4.92 0 2.755 1.79 1 4 1"/>
                                    </svg>
                                    <svg v-else-if="!bookmark.isFavorite" xmlns="http://www.w3.org/2000/svg" width="28" height="28" fill="#fff5" class="bi bi-suit-heart" viewBox="0 0 16 16">
                                        <path d="m8 6.236-.894-1.789c-.222-.443-.607-1.08-1.152-1.595C5.418 2.345 4.776 2 4 2 2.324 2 1 3.326 1 4.92c0 1.211.554 2.066 1.868 3.37.337.334.721.695 1.146 1.093C5.122 10.423 6.5 11.717 8 13.447c1.5-1.73 2.878-3.024 3.986-4.064.425-.398.81-.76 1.146-1.093C14.446 6.986 15 6.131 15 4.92 15 3.326 13.676 2 12 2c-.777 0-1.418.345-1.954.852-.545.515-.93 1.152-1.152 1.595zm.392 8.292a.513.513 0 0 1-.784 0c-1.601-1.902-3.05-3.262-4.243-4.381C1.3 8.208 0 6.989 0 4.92 0 2.755 1.79 1 4 1c1.6 0 2.719 1.05 3.404 2.008.26.365.458.716.596.992a7.6 7.6 0 0 1 .596-.992C9.281 2.049 10.4 1 12 1c2.21 0 4 1.755 4 3.92 0 2.069-1.3 3.288-3.365 5.227-1.193 1.12-2.642 2.48-4.243 4.38z"/>
                                    </svg>
                                </div>
                            </div>
                </li>
            </ul>
            <div v-else class="text-container">
                <p>Your bookmarks are empty</p>
            </div>
        </div>
         <div class="close-block" @click="closeBookmark">
                <svg xmlns="http://www.w3.org/2000/svg" width="28" height="28" fill="#fff" class="bi bi-x-circle-fill" viewBox="0 0 16 16">
                    <path d="M16 8A8 8 0 1 1 0 8a8 8 0 0 1 16 0M5.354 4.646a.5.5 0 1 0-.708.708L7.293 8l-2.647 2.646a.5.5 0 0 0 .708.708L8 8.707l2.646 2.647a.5.5 0 0 0 .708-.708L8.707 8l2.647-2.646a.5.5 0 0 0-.708-.708L8 7.293z"/>
                </svg>
        </div>
    </div>
</template>

<style scoped>

    .bookmark-content {
        position: relative;
        z-index: 1001;
        padding: 20px 0;
        width: 850px;
        min-height: 300px;
        border-radius: 15px;
        border: 1px solid #cccccca3;
        background-color: #17193dd5;
        box-shadow: 0 0 45px 10px #000000d8;
    }

    .bookmark-content .heading {
        font-family: 'Roboto', sans-serif;
        letter-spacing: 1.5px;
        position: sticky;
        top: 0;
        z-index: 200;
        padding: 10px 0;
        background-color: rgba(2, 26, 92, 0.805);
        border-top: 1px solid #ccc;
        border-bottom: 1px solid #ccc;
    }

    .bookmark-content .heading .header {
        color: #fff;
        text-align: center;
    }

    .bookmark-content .bookmarks-list {
        padding: 25px;
        display: flex;
        flex-direction: column;
        align-items: center;
        gap: 20px;
        max-width: 100%;
        max-height: 250px;
        overflow-y: scroll;
    }

    .bookmarks-list-content .text-container p {
        font-size: 15px;
        font-weight: 400;
        font-style: italic;
        color: #7599d2dd;
        font-family: 'Poppins', sans-serif;
        text-align: center;
        margin-top: 100px;
    }

    .bookmark-content ul {
        list-style-type: none;
        font-family: 'Roboto', sans-serif;
    }

    .bookmark-content ul .model {
        width: 100%;
        height: 83px;
        display: flex;
        border-radius: 10px;
        background-color: rgb(34, 53, 103);
        border: 1px solid #cccccc8b;
        position: relative;
        z-index: 150;
        transition: all 0.3s ease;
        box-shadow: 2px 2px 8px #000;
    }

    .bookmark-content ul .model:hover {
        transform: scale(1.03);
        cursor: pointer;
        background-color: #3e61ba;
        box-shadow: 0 0 30px #7a92cd3a;
    }

    .bookmark-content ul .model .bmw-img-box{
        max-width: 150px;
        max-height: auto;
        padding: 5px;
        display: flex;
        align-items: center;
        margin: 0 10px;
        overflow: hidden;
        box-sizing: border-box;
    }

    .bookmark-content ul .model .bmw-img-box img {
        position: relative;
        width: 110%;
        height: 150%;
        object-fit: cover;
        transform: translateY(-5px);
    }

    .info-content {
        display: flex;
        align-items: center;
        width: 80%;
        margin-left: 5px;
    }

    .info-content .info-heading {
        display: block;
        padding: 0 5px;
        align-content: center;
        border-left: 1px solid #c0cbff5c;
        border-right: 1px solid #c0cbff5c;
        min-width: 150px;
        height: 85px;
    }

    .info-content .info-heading h4 {
        font-size: 18px;
        font-style: italic;
        text-align: center;
        color: rgb(255, 255, 255);
        line-height: 22px;
    }

    .info-content .char-container {
        border-right: 1px solid #c0cbff5c;
        height: 100%;
        min-width: 300px;
        display: block;
        align-content: center;
        padding: 0 20px;
    }

    .info-content .char-list {
        list-style-type: none;
        display: grid;
        grid-template-columns: repeat(2, 1fr);
        gap: 10px;
    }

    .info-content .char-list li {
        color: rgb(163, 163, 163);
        font-size: 14px;
        font-style: italic;
        font-weight: 600;
        text-align: center;
        display: block;
        align-content: center;
    }

    .bookmarks-list li .fav-block {
        position: relative;
        height: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
        margin: 0 35px;
    }
    
    .bookmark-content .heading .qnt-cards {
        position: absolute;
        padding: 5px 10px;
        color: #fff;
        z-index: 500;
        bottom: 10px;
        left: 5px;
        border: 1px solid #cccccc75;
        border-radius: 15px;
        font-family: 'Roboto', sans-serif;
        font-size: 12px;
        font-weight: 600;
    }

    .bookmark-container .close-block {
        position: absolute;
        z-index: 1005;
        top: -10px;
        right: -5px;
        transition: all 0.2s ease-out;
    }

    .bookmark-container .close-block:hover {
        transform: scale(0.9);
        cursor: pointer;
        filter: brightness(80%);
    }

    
</style>

<script>
export default {
    name: 'Bookmark',
    props: {
        bookmarks: Array,
        numCards: Number
    },
    emits: ['close-at-bookmark'],
    methods: {
        closeBookmark() {
            this.$emit('close-at-bookmark');
        }        
    }     
}
</script>
