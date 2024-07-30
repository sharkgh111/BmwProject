<template>
    <div class="content-block">
        <div v-show="currentIndex === 1" class="main-content-wrap">
            <div class="main-content">
                <div class="main-text-block">
                    <div class="heading-content">
                        <img src="/logo/bmwicon.png" alt="BMWlogo">
                            <h1 class="heading">Bayerische Motoren Werke AG</h1>
                    </div>
                        <p class="text">
                            German manufacturer of cars, motorcycles and engines, founded in 1916. 
                                The company is one of the world's leading automakers, 
                                known for its innovative approach to design and technology. 
                             BMW's headquarters are located in Munich, Germany.
                        </p>
                        <p class="text">
                            Throughout its history, BMW has introduced many technological innovations, 
                                such as the xDrive all-wheel drive system, 
                                intelligent driver assistance systems and 
                            highly efficient hybrid and electric vehicles.
                        </p>
                </div>
                <div class="main-img-box">
                    <img src="/images/bmwmain.jpeg" class="first-main-image">
                </div>
            </div>
        </div>
        <div v-show="currentIndex === 2" class="main-content-wrap">
            <div class="main-content">
                <div class="main-text-block">
                        <p class="text">
                            After World War I, the company switched to producing motorcycles and cars.
                                BMW's first motorcycle, the R32, was released in 1923. In 1928, BMW acquired the automobile
                                plant in Eisenach and began production of its first car, the BMW 3/15,
                            which was a licensed copy of the British Austin 7.
                        </p>
                        <p class="text">
                            During the 1930s, BMW significantly expanded its model range, 
                                introducing several new car and motorcycle models. 
                                The famous inline six-cylinder engines were developed during this period.
                        </p>
                </div>
                <div class="main-img-box">
                        <img src="/images/bmwmain2.jpeg" class="second-main-image">
                </div>
            </div>
        </div>
        <div v-show="currentIndex === 3" class="main-content-wrap">
            <div class="main-content">
                <div class="main-text-block">
                        <p class="text">
                            In 1962, BMW introduced the "Neue Klasse" series of cars, 
                                which marked a turning point for the company. These models, 
                                including the BMW 1500 and 2002, featured modern design, advanced technology and high performance. 
                                "Neue Klasse" helped BMW regain financial stability and build a reputation as a manufacturer of sports and quality cars.
                        </p>
                        <p class="text">
                           During the 1970s, BMW continued to expand its model range,
                                introducing new series: Series 5 (1972), Series 3 (1975), Series 6 (1976) and Series 7 (1977).
                                These cars strengthened BMW's position as a premium manufacturer.
                        </p>
                </div>
                <div class="main-img-box">
                        <img src="/images/bmwmain3.avif" class="third-main-image">
                </div>
            </div>
        </div>
        <div v-show="currentIndex === 4" class="main-content-wrap">
            <div class="main-content">
                <div class="main-text-block">
                        <p class="text">
                            In the 1990s, BMW continued its expansion into the global market,
                                opening new factories and representative offices around the world.
                                In 1994, BMW acquired the British company Rover Group,
                                although the move was unsuccessful and Rover was sold in 2000.
                        </p>
                        <p class="text">
                            In recent decades, BMW has been actively developing
                                electric and hybrid technologies. The BMW i series was introduced in 2013,
                                including the all-electric BMW i3 and the BMW i8 hybrid sports car.
                                The company is also investing in the development of autonomous driving and connectivity systems
                                cars to the Internet.
                        </p>
                </div>
                <div class="main-img-box">
                        <img src="/images/bmwmain4.jpg" class="">
                </div>
            </div>
        </div>
        <div class="btn-block">
            <div class="arrow-left" @click="slidePage(-1)" >
                <div class="arrow">
                    <svg xmlns="http://www.w3.org/2000/svg" width="48" height="48" fill="#fff6" class="bi bi-arrow-bar-left" viewBox="0 0 16 16">
                        <path fill-rule="evenodd" d="M12.5 15a.5.5 0 0 1-.5-.5v-13a.5.5 0 0 1 1 0v13a.5.5 0 0 1-.5.5M10 8a.5.5 0 0 1-.5.5H3.707l2.147 2.146a.5.5 0 0 1-.708.708l-3-3a.5.5 0 0 1 0-.708l3-3a.5.5 0 1 1 .708.708L3.707 7.5H9.5a.5.5 0 0 1 .5.5"/>
                    </svg>
                </div>
            </div>
            <div class="arrow-right" @click="slidePage(1)" >
                <div class="arrow">
                    <svg xmlns="http://www.w3.org/2000/svg" width="48" height="48" fill="#fff6" class="bi bi-arrow-bar-right" viewBox="0 0 16 16">
                        <path fill-rule="evenodd" d="M6 8a.5.5 0 0 0 .5.5h5.793l-2.147 2.146a.5.5 0 0 0 .708.708l3-3a.5.5 0 0 0 0-.708l-3-3a.5.5 0 0 0-.708.708L12.293 7.5H6.5A.5.5 0 0 0 6 8m-2.5 7a.5.5 0 0 1-.5-.5v-13a.5.5 0 0 1 1 0v13a.5.5 0 0 1-.5.5"/>
                    </svg>
                </div>
            </div>
        </div>
    </div>
</template>

<style scoped>
    
    .content-block {
        overflow-x: hidden;
        max-width: 100%;
        position: relative;
    }

    .main-content-wrap {
        width: 100%;
        background: radial-gradient(circle at right, rgb(0, 32, 101) 0%, rgb(0, 10, 49) 60%, #000000d5 100%);
        border-top: 1px solid #c0cbff62;
        border-bottom: 1px solid #c0cbff62;
        padding: 55px 0;
    }

    .main-content {
        width: 100%;
        color: #fff;
        display: flex;
        align-items: center;
        justify-content: space-evenly;
    }

    .main-img-box {
        width: 650px;
        padding-right: 30px;
        transition: all 0.4s ease;
        filter: drop-shadow(4px 4px 15px #000);
        display: block;
        align-content: center;
    }

    .main-text-block {
        text-align: center;
        display: flex;
        flex-direction: column;
        justify-content: center;
        margin-left: 30px;
        width: 540px;
    }

    .heading-content {
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: column;
        gap: 15px;
        margin-bottom: 10px;
    }

    .heading-content img {
        width: 100px;
    }

    .main-text-block .text {
        font-size: 18px;
        font-style: italic;
        font-family: 'Roboto', sans-serif;
        line-height: 1.6em;
        font-weight: 600;
        margin-bottom: 8px;
    }

    .main-text-block h1{
        font-size: 28px;
        font-family: 'Poppins', sans-serif;
        font-style: italic;
        color: rgb(0, 166, 255);
        text-shadow: 2px 2px 15px #000;
    }

    .main-img-box img {
        width: 100%;
        height: auto;
        transition: all 0.6s ease;
        clip-path: polygon(20% 0, 100% 1%, 100% 100%, 0 100%);
        filter: brightness(80%);
    }

     .main-img-box:hover img {
        transform: scale(1.05);
        cursor: pointer;
        filter: brightness(100%);
     }

     .btn-block {
        position: absolute;
        z-index: 500;
        top: 45%;
        width: 100%;
        gap: 90%;
        display: flex;
        justify-content: space-around;
        pointer-events: none;
    }

    .btn-block .arrow {
        pointer-events: all;
        cursor: pointer;
        transition: all 0.3s ease;
        filter: brightness(40%);
    }

    .content-block:hover .arrow {
        filter: brightness(70%);
    }

    .btn-block .arrow:hover {
        transform: scale(1.1);
        filter: brightness(110%);
    }

    @media (max-width: 1900px) {
        .main-text-block .text {
            font-size: 20px;
        }
    }

    @media (max-width: 1000px) {
        .main-content {
            flex-direction: column;
        }

        .main-img-box img {
            clip-path: none;
            border-radius: 10px;
        }

        .main-img-box {
            padding: 0;
            width: 500px;
        }

        .main-text-block {
            margin: 0;
            margin-bottom: 30px;
        }

        .main-text-block p.text {
            font-size: 20px;
        }
    }

</style>

<script>
export default {
    data() {
        return {
            currentIndex: 1
        }
    },
    methods: {
        slidePage(n) {
            this.currentIndex += n;
            if (this.currentIndex < 1) {
                this.currentIndex = 4;
            } else if (this.currentIndex > 4) {
                this.currentIndex = 1;
            }
        }
    }
}
</script>