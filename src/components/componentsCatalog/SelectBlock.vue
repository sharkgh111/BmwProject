<template>
                <ul class="select-seria-block">
                    <li class="img-box" v-for="seria in series" :key="seria.name" @click="selectedSeria(seria.name)">
                        <img :src="seria.url" :alt="seria.name">
                    </li>
                </ul>
</template>

<style scoped>

    .select-seria-block {
        list-style-type: none;
        width: 170px;
        height: 400px;
        padding: 25px 20px;
        margin-right: 20px;
        background: linear-gradient(45deg, rgb(37, 75, 173), rgb(16, 28, 96));
        box-shadow: 0 0 20px #000;
        border-radius: 0 10px 10px 0;
        display: flex;
        flex-direction: column;
        justify-content: space-around;
        align-items: center;
        overflow-y: scroll;
    }

    .select-seria-block .img-box {
        width: 90px;
        height: auto;
        object-fit: cover;
        margin: 0 10px;
    }

    .select-seria-block .img-box img {
        transition: all 0.3s ease;
        height: 100%;
        width: 100%;
        object-fit: contain; /* Масштабирование изображения с сохранением пропорций */
        display: block;
        margin: 0 auto;
        filter: drop-shadow(2px 3px 8px #000);
    }

    .img-box img:hover {
        cursor: pointer;
        transform: scale(1.2) translate(-3px, -3px);
        filter: drop-shadow(2px 3px 10px rgba(185, 234, 255, 0.412));
    }

    .select-seria-block
    .img-box:nth-child(1) {
        width: 100px;
    }

    .select-seria-block
    .img-box:nth-last-child(-n+2) {
        width: 110px;
    }

    .select-seria-block img {
        width: 100%;
    }

    @media (max-width: 1330px) {
        .select-seria-block {
            flex-direction: row;
            width: 100%;
            margin: 0;
            height: auto;
            flex-wrap: wrap;
            border-top: 1px solid #ccc;
            border-bottom: 1px solid #ccc;
            padding: 5px 0;
        }
    }

</style>

<script>
export default {
    name: 'SelBlock',
    props: ['series'],
    methods: {
        selectedSeria(seriaName) {
        this.$emit('select-series', seriaName);
        }
        
    }
}
</script>