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
        transition: filter 0.2s ease;
    }

    .content-container .image .overlay-text {
        position: absolute;
        padding: 10px;
        top: 80px;
        z-index: 600;
    }

    .content-container .image .overlay-text .heading {
        position: relative;
        color: transparent;
        font-size: 30px;
        padding: 0 15px;
        font-style: italic;
        margin-bottom: 25px;
        transition: left 0.4s ease, opacity 0.5s ease, background-position 3s ease, filter 0.9s ease;
        background: linear-gradient(to left, hsl(180, 100%, 84%), hsl(226, 71%, 56%));
        background-size: 200% 100%;
        background-clip: text;
        background-position: 0;
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
        background-position: -100%;
        filter: drop-shadow(0 0 1rem #a1cae9);
    }

    .content-container .image:hover::before {
        background-color: rgba(0, 0, 0, 0.63);
    }

    .text-block {
        margin: 0 20px;
        color: #fff;
    }

    .text-block .heading {
        --bmw-main-color-: rgb(0, 166, 255);
        font-style: italic;
        margin-bottom: 15px;
        color: var(--bmw-main-color-);
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
                { img: '/images/bmwaboutmain1.jpg', alt: 'BMWmain1', grayscale: 0, header: 'Meaning of the logo', text: 'The BMW logo, blue and white, resembles an aircraft propeller. This design was chosen to honor the company`s early work in the aviation industry.' },
                { img: '/images/bmwaboutmain2.jpg', alt: 'BMWmain2', grayscale: 0, header: 'Iconic models', text: 'The BMW 3 Series has become one of the brand`s most successful and well-known models since its first version in 1975, renowned for its dynamics and handling.' },
                { img: '/images/bmwaboutmain3.jpg', alt: 'BMWmain3', grayscale: 0, header: 'The first electric car', text: 'BMW introduced its first electric car, the i3, in 2013. The car was designed as an eco-friendly solution and was one of the first in the brand`s line of electric vehicles.' },
                { img: '/images/bmwaboutmain4.jpg', alt: 'BMWmain4', grayscale: 0, header: 'Driving pleasure', text: 'BMW is known for its philosophy of "The Ultimate Driving Machine", which reflects their commitment to creating cars that offer outstanding handling and driving experience.' },
                { img: '/images/bmwaboutmain5.jpg', alt: 'BMWmain5', grayscale: 0, header: 'Innovative technologies', text: 'BMW is actively developing autonomous driving technologies and intelligent driver assistance systems. Their iDrive system, introduced in 2001, was one of the first successful examples of an intuitive interface for controlling car functions.' },
                { img: '/images/bmwaboutmain6.jpg', alt: 'BMWmain6', grayscale: 0, header: 'History of the company', text: 'BMW was founded in 1916 as a manufacturer of aircraft engines. It was only after World War I that the company switched to producing motorcycles and cars.' }
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