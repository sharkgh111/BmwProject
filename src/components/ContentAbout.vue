<template>
    <div class="content-about">
        <div class="container">
            <div class="text-block">
                <div class="logo-container">
                        <div class="logo">
                            <img src="/logo/bmwicon.png" alt="BMWlogo">
                        </div>
                </div>
                <h2 class="heading">BMW (Bayerische Motoren Werke AG)</h2>
                    <p> 
                        It is a German company that manufactures automobiles, motorcycles, and engines.
                        It was founded in 1916 and is based in Munich, Germany.
                        BMW is one of the world's leading automobile brands and is known for its high-quality, high-performance vehicles.
                    </p>
            </div>
                <div class="content-container" ref="imageContainer">
                    <div class="image" v-for="(item, index) in images" :key="index">
                        <img :src="item.img" :alt="item.alt" :style="{ filter: `grayscale(${item.grayscale}%)` }" >
                            <div class="overlay-text">
                                <h3 class="heading">{{ item.header }}</h3>
                                    <p class="par">{{ item.text }}</p>
                            </div>
                    </div>
                </div>
            <div class="text-block">
                <h2>Mission and Vision</h2>
                    <h3 class="heading">Mission</h3>
                        <p class="text">
                            BMW aims to ensure that every aspect of its activities reflects 
                            its commitment to the highest standards of quality, innovation and 
                            customer satisfaction. The company's mission is to create cars and 
                            services that not only meet but also exceed customer expectations, 
                            while providing driving pleasure and improving quality of life. 
                            BMW aims to provide products and services that embody a combination 
                            of high performance, elegant design and advanced technology.
                        </p>
                    <h3 class="heading">Vision</h3>
                        <p class="text">
                            BMW aims to be a leader in the premium segment of the automobile market, 
                            setting standards in sustainable and responsible business practices. 
                            The company's vision includes the following key aspects:
                        </p>
                            <ol class="list">
                                <li>
                                    <h3>Innovation and Technological Excellence:</h3>
                                        <p>
                                            BMW continues to invest in research and development 
                                            to stay at the forefront of technology. 
                                            This includes the development of electric and 
                                            hybrid powertrains, autonomous driving systems 
                                            and connected cars.
                                        </p>
                                </li>
                                <li>
                                    <h3>Sustainability and Eco-Friendliness:</h3>
                                        <p>
                                            BMW is committed to sustainability and is 
                                            actively working to reduce the carbon footprint 
                                            of its products and production processes. 
                                            The company is committed to a complete 
                                            transition to renewable energy sources and 
                                            the introduction of recycling technologies.
                                        </p>
                                </li>
                                <li>
                                    <h3>Customer focus:</h3>
                                        <p>
                                            The customer is at the center of BMW’s 
                                            attention. The company is constantly improving 
                                            its service and products to offer customers 
                                            individual solutions and the highest level of service. 
                                            Every BMW customer should feel special and receive a 
                                            unique experience of interaction with the brand.
                                        </p>
                                </li>
                                <li>
                                    <h3>Global Presence:</h3>
                                        <p>
                                            BMW continues to expand its presence in global markets, 
                                            strengthening its position in key regions and entering new markets. 
                                            The company strives to be recognized as a leader in every segment in which it is represented.
                                        </p>
                                </li>
                                <li>
                                    <h3>Corporate Social Responsibility:</h3>
                                        <p>
                                            BMW actively participates in social and charitable projects, 
                                            supporting initiatives aimed at improving society. 
                                            The company strives to be an example of responsible business that contributes 
                                            to the development of social and environmental initiatives.
                                        </p>
                                </li>
                            </ol>
                        <p class="text">
                            These principles and goals form the basis of BMW's development strategy, 
                            which is aimed at long-term success and the creation of value for customers, employees and society as a whole.
                        </p>
            </div>
        </div>
    </div>
</template>

<style scoped>

    .container {
        padding: 20px 0;
        background: rgb(21,51,125);
        background: linear-gradient(99deg, rgb(0, 20, 70) 20%, rgba(0,12,37,1) 70%);
        font-family: 'Poppins', sans-serif;
    }

    .container p:not(.text):not(ol p) {
        padding: 20px 150px;
        font-size: 16px;
        color: #ffffffc1;
        text-align: center;
    }

    .container .logo-container {
        width: 100%;
        display: flex;
        align-items: center;
        justify-content: center;
        margin-bottom: 30px;
        z-index: 800;
    }

    .container .logo {
        max-width: 120px;
        max-height: 120px;
    }

    .logo img {
        width: 100%;
        height: 100%;
    }

    .container .content-container {
        position: relative;
        display: grid;
        place-items: center;
        grid-template-columns: repeat(2, 1fr);
        max-width: 100%;
        margin: 35px 0;
        border-top: 1px solid #ccc;
        border-bottom: 1px solid #ccc;
    }

    .content-container .image {
        position: relative;
        width: 100%;
        height: 380px;
        overflow: hidden;
        cursor: pointer;
        z-index: 300;
    }

    .content-container .image::before {
        content: '';
        position: absolute;
        top: 0;
        left: 0;
        width: 100%;
        height: 100%;
        background-color: #ffffff00;
        z-index: 400;
        pointer-events: none;
        transition: all 0.4s ease;
    }

    .content-container .image img {
        display: block;
        width: 100%;
        height: 100%;
        object-fit: cover;
        transition: filter 0.2s ease; /* переход для фильтра */;
    }

    .content-container .image .overlay-text {
        position: absolute;
        padding: 10px;
        top: 80px;
        text-shadow: 0 0 10px #000;
        z-index: 600;
    }

    .content-container .image .overlay-text .heading {
        position: relative;
        color: #bbedff;
        font-size: 30px;
        padding: 0 15px;
        font-style: italic;
        margin-bottom: 25px;
        transition: left 0.4s ease, opacity 0.5s ease;
    }
    
    .content-container .image .overlay-text .par {
        position: relative;
        color: #ffffff;
        font-weight: 600;
        font-size: 17px;
        padding: 0 45px;
        line-height: 1.6em;
        font-style: italic;
        transition: left 0.3s ease, opacity 0.3s ease;
        transition-delay: 0.55s;
    }

    .content-container .overlay-text .heading, .par {
        left: -100%;
        opacity: 0;
    }

    .content-container .image:hover 
    .overlay-text .heading,
    .image:hover .overlay-text .par {
        left: 0;
        opacity: 1;
    }

    .content-container .image:hover::before {
        background-color: rgba(0, 0, 0, 0.63);
    }

    .text-block {
        margin: 0 20px;
        color: #fff;
    }

    .text-block .heading {
        font-style: italic;
        margin-bottom: 15px;
        color: rgb(0, 166, 255);
    }

    .text-block h2 {
        text-align: center;
        font-style: italic;
        font-size: 26px;
    }

    .text-block .text {
        font-size: 15px;
        color: #ffffffd2;
        font-weight: 600;
        word-spacing: 1.5px;
        padding: 0 30px;
        margin-bottom: 15px;
    }

    ol {
        display: flex;
        flex-direction: column;
        gap: 20px;
        margin: 0 20px;
        padding: 20px 0;
    }

    ol li h3 {
        margin-bottom: 10px;
        font-size: 16px;
    }

    ol li p {
        color: #ffffffd2;
        font-size: 16px;
        font-style: italic;
    }

</style>

<script>
export default {
    data() {
        return {
            images: [
                { img: '/images/bmwaboutmain1.jpg', alt: 'BMWmain1', grayscale: 0, header: 'Значение логотипа', text: 'Логотип BMW, синий и белый, напоминает авиационный пропеллер. Этот дизайн был выбран в честь первоначальной деятельности компании в авиационной промышленности.' },
                { img: '/images/bmwaboutmain2.jpg', alt: 'BMWmain2', grayscale: 0, header: 'Иконные модели', text: 'BMW 3 Series, начиная с первой версии в 1975 году, стала одной из самых успешных и известных моделей марки, известной своей динамикой и управляемостью.' },
                { img: '/images/bmwaboutmain3.jpg', alt: 'BMWmain3', grayscale: 0, header: 'Первый электромобиль', text: 'BMW представила свой первый электромобиль, i3, в 2013 году. Этот автомобиль был спроектирован как экологически чистое решение и стал одним из первых в линейке электромобилей марки.' },
                { img: '/images/bmwaboutmain4.jpg', alt: 'BMWmain4', grayscale: 0, header: 'Удовольствия от вождения', text: 'BMW известна своей философией "удовольствия от вождения" (The Ultimate Driving Machine), которая отражает их стремление создавать автомобили, которые предлагают выдающуюся управляемость и драйвовые ощущения.' },
                { img: '/images/bmwaboutmain5.jpg', alt: 'BMWmain5', grayscale: 0, header: 'Иновационные технологии', text: 'BMW активно разрабатывает технологии автономного вождения и интеллектуальных систем помощи водителю. Их система iDrive, представленная в 2001 году, стала одним из первых успешных примеров интуитивно понятного интерфейса для управления автомобильными функциями.' },
                { img: '/images/bmwaboutmain6.jpg', alt: 'BMWmain6', grayscale: 0, header: 'История компании', text: 'BMW была основана в 1916 году как производитель авиационных двигателей. Только после Первой мировой войны компания переключилась на производство мотоциклов и автомобилей.' }
            ],
            effectWindowHeight: 700
        }
    },
    mounted() {
        this.$nextTick(() => {
            window.addEventListener('scroll', this.handleScroll);
            this.handleScroll(); // Вызываем сразу после монтирования
        });
    },
    beforeUnmount() {
        window.removeEventListener('scroll', this.handleScroll);
    },
    methods: {
        handleScroll() {
            const container = this.$refs.imageContainer;
            if (!container) return;

            const rect = container.getBoundingClientRect();
            const isVisible = (rect.top < this.effectWindowHeight && rect.bottom >= 0);
            
            if (isVisible) {
                const containerTop = Math.max(0, rect.top);
                const containerBottom = Math.min(this.effectWindowHeight, rect.bottom);
                const visibleHeight = containerBottom - containerTop;
                const scrollPercentage = 1 - (visibleHeight / this.effectWindowHeight);

                this.images.forEach((image) => {
                    const startGrayscale = 0;
                    const endGrayscale = 200;
                    image.grayscale = startGrayscale + (endGrayscale - startGrayscale) * scrollPercentage;
                });
            } else {
                // Если контейнер не виден, устанавливаем максимальное значение grayscale
                this.images.forEach((image) => {
                    image.grayscale = 200;
                });
            }
        }
    }
}
</script>