<template>
  <footer>
    <div class="footer-content">
        <div class="header-text-block">
            <h2>© 2024 BMW. All rights reserved</h2>
        </div>
        <div class="list-block">
            <div class="contacts-block">
                <h3>Contacts</h3>
                    <ul class="contacts">
                        <li>
                            Address: #
                        </li>
                        <li>
                            Telephone: #
                        </li>
                        <li>
                            Email: #
                        </li>
                    </ul>
            </div>
            <div class="account-block">
                <h3>Account</h3>
                    <ul class="account">
                        <li @click="activeProfileAdd(1)">
                            <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" fill="currentColor" class="bi bi-person-fill-down" viewBox="0 0 16 16">
                                <path d="M12.5 9a3.5 3.5 0 1 1 0 7 3.5 3.5 0 0 1 0-7m.354 5.854 1.5-1.5a.5.5 0 0 0-.708-.708l-.646.647V10.5a.5.5 0 0 0-1 0v2.793l-.646-.647a.5.5 0 0 0-.708.708l1.5 1.5a.5.5 0 0 0 .708 0M11 5a3 3 0 1 1-6 0 3 3 0 0 1 6 0"/>
                                <path d="M2 13c0 1 1 1 1 1h5.256A4.5 4.5 0 0 1 8 12.5a4.5 4.5 0 0 1 1.544-3.393Q8.844 9.002 8 9c-5 0-6 3-6 4"/>
                            </svg>
                            <p>
                                Sign Up
                            </p>
                        </li>
                        <li @click="activeProfileAdd(2)">
                            <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" fill="currentColor" class="bi bi-person-fill-gear" viewBox="0 0 16 16">
                                <path d="M11 5a3 3 0 1 1-6 0 3 3 0 0 1 6 0m-9 8c0 1 1 1 1 1h5.256A4.5 4.5 0 0 1 8 12.5a4.5 4.5 0 0 1 1.544-3.393Q8.844 9.002 8 9c-5 0-6 3-6 4m9.886-3.54c.18-.613 1.048-.613 1.229 0l.043.148a.64.64 0 0 0 .921.382l.136-.074c.561-.306 1.175.308.87.869l-.075.136a.64.64 0 0 0 .382.92l.149.045c.612.18.612 1.048 0 1.229l-.15.043a.64.64 0 0 0-.38.921l.074.136c.305.561-.309 1.175-.87.87l-.136-.075a.64.64 0 0 0-.92.382l-.045.149c-.18.612-1.048.612-1.229 0l-.043-.15a.64.64 0 0 0-.921-.38l-.136.074c-.561.305-1.175-.309-.87-.87l.075-.136a.64.64 0 0 0-.382-.92l-.148-.045c-.613-.18-.613-1.048 0-1.229l.148-.043a.64.64 0 0 0 .382-.921l-.074-.136c-.306-.561.308-1.175.869-.87l.136.075a.64.64 0 0 0 .92-.382zM14 12.5a1.5 1.5 0 1 0-3 0 1.5 1.5 0 0 0 3 0"/>
                            </svg>
                            <p>
                                Change account
                            </p>
                        </li>
                    </ul>
            </div>
            <div class="soc-media-block">
                <h3>Social media</h3>
                    <ul class="soc-medias">
                        <li>
                            <a href="https://www.facebook.com/BMW/?locale=ru_RU" target="_blank">
                                <svg xmlns="http://www.w3.org/2000/svg" width="15" height="15" fill="currentColor" class="bi bi-facebook" viewBox="0 0 16 16">
                                    <path d="M16 8.049c0-4.446-3.582-8.05-8-8.05C3.58 0-.002 3.603-.002 8.05c0 4.017 2.926 7.347 6.75 7.951v-5.625h-2.03V8.05H6.75V6.275c0-2.017 1.195-3.131 3.022-3.131.876 0 1.791.157 1.791.157v1.98h-1.009c-.993 0-1.303.621-1.303 1.258v1.51h2.218l-.354 2.326H9.25V16c3.824-.604 6.75-3.934 6.75-7.951"/>
                                </svg>
                                <p class="text">
                                    Facebook
                                </p>
                            </a>
                        </li>
                        <li>
                            <a href="https://www.instagram.com/bmw/" target="_blank">
                                <svg xmlns="http://www.w3.org/2000/svg" width="15" height="15" fill="currentColor" class="bi bi-instagram" viewBox="0 0 16 16">
                                    <path d="M8 0C5.829 0 5.556.01 4.703.048 3.85.088 3.269.222 2.76.42a3.9 3.9 0 0 0-1.417.923A3.9 3.9 0 0 0 .42 2.76C.222 3.268.087 3.85.048 4.7.01 5.555 0 5.827 0 8.001c0 2.172.01 2.444.048 3.297.04.852.174 1.433.372 1.942.205.526.478.972.923 1.417.444.445.89.719 1.416.923.51.198 1.09.333 1.942.372C5.555 15.99 5.827 16 8 16s2.444-.01 3.298-.048c.851-.04 1.434-.174 1.943-.372a3.9 3.9 0 0 0 1.416-.923c.445-.445.718-.891.923-1.417.197-.509.332-1.09.372-1.942C15.99 10.445 16 10.173 16 8s-.01-2.445-.048-3.299c-.04-.851-.175-1.433-.372-1.941a3.9 3.9 0 0 0-.923-1.417A3.9 3.9 0 0 0 13.24.42c-.51-.198-1.092-.333-1.943-.372C10.443.01 10.172 0 7.998 0zm-.717 1.442h.718c2.136 0 2.389.007 3.232.046.78.035 1.204.166 1.486.275.373.145.64.319.92.599s.453.546.598.92c.11.281.24.705.275 1.485.039.843.047 1.096.047 3.231s-.008 2.389-.047 3.232c-.035.78-.166 1.203-.275 1.485a2.5 2.5 0 0 1-.599.919c-.28.28-.546.453-.92.598-.28.11-.704.24-1.485.276-.843.038-1.096.047-3.232.047s-2.39-.009-3.233-.047c-.78-.036-1.203-.166-1.485-.276a2.5 2.5 0 0 1-.92-.598 2.5 2.5 0 0 1-.6-.92c-.109-.281-.24-.705-.275-1.485-.038-.843-.046-1.096-.046-3.233s.008-2.388.046-3.231c.036-.78.166-1.204.276-1.486.145-.373.319-.64.599-.92s.546-.453.92-.598c.282-.11.705-.24 1.485-.276.738-.034 1.024-.044 2.515-.045zm4.988 1.328a.96.96 0 1 0 0 1.92.96.96 0 0 0 0-1.92m-4.27 1.122a4.109 4.109 0 1 0 0 8.217 4.109 4.109 0 0 0 0-8.217m0 1.441a2.667 2.667 0 1 1 0 5.334 2.667 2.667 0 0 1 0-5.334"/>
                                </svg>
                                <p class="text">
                                    Instagram
                                </p>
                            </a>
                        </li>
                        <li>
                            <a href="https://t.me/s/bmwcompany?before=2140" target="_blank">
                                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-telegram" viewBox="0 0 16 16">
                                    <path d="M16 8A8 8 0 1 1 0 8a8 8 0 0 1 16 0M8.287 5.906q-1.168.486-4.666 2.01-.567.225-.595.442c-.03.243.275.339.69.47l.175.055c.408.133.958.288 1.243.294q.39.01.868-.32 3.269-2.206 3.374-2.23c.05-.012.12-.026.166.016s.042.12.037.141c-.03.129-1.227 1.241-1.846 1.817-.193.18-.33.307-.358.336a8 8 0 0 1-.188.186c-.38.366-.664.64.015 1.088.327.216.589.393.85.571.284.194.568.387.936.629q.14.092.27.187c.331.236.63.448.997.414.214-.02.435-.22.547-.82.265-1.417.786-4.486.906-5.751a1.4 1.4 0 0 0-.013-.315.34.34 0 0 0-.114-.217.53.53 0 0 0-.31-.093c-.3.005-.763.166-2.984 1.09"/>
                                </svg>
                                <p class="text">
                                    Telegram
                                </p>
                            </a>
                        </li>
                        <li>
                            <a href="https://x.com/BMW?ref_src=twsrc%5Egoogle%7Ctwcamp%5Eserp%7Ctwgr%5Eauthor" target="_blank">
                                <svg xmlns="http://www.w3.org/2000/svg" width="16" height="16" fill="currentColor" class="bi bi-twitter-x" viewBox="0 0 16 16">
                                    <path d="M12.6.75h2.454l-5.36 6.142L16 15.25h-4.937l-3.867-5.07-4.425 5.07H.316l5.733-6.57L0 .75h5.063l3.495 4.633L12.601.75Zm-.86 13.028h1.36L4.323 2.145H2.865z"/>
                                </svg>
                                <p class="text">
                                    X | Twitter
                                </p>
                            </a>
                        </li>
                    </ul>
            </div>
            <div class="useful-links-block">
                <h3>Useful links</h3>
                    <ul class="useful-links">
                        <li>
                            <a href="#">
                                Career at BMW
                            </a>
                        </li>
                        <li>
                            <a href="#">
                                News and events
                            </a>
                        </li>
                        <li>
                            <a href="#">
                                Car configurator
                            </a>
                        </li>
                        <li>
                            <a href="#">
                                Services
                            </a>
                        </li>
                        <li>
                            <a href="#">
                                Accessories
                            </a>
                        </li>
                    </ul>
            </div>
        </div>
        <div v-if="activeLogin == 1" class="input-form-container">
            <form>
                <div class="form-wrapper">
                    <div class="logo-container">
                        <img src="/logo/bmwicon.png" alt="Logo">
                    </div>
                    <div class="heading-block">
                        <h2>SIGN UP</h2>
                    </div>
                    <div class="inputs-container">
                        <div class="email input-box">
                            <input type="email" placeholder="" id="email" v-model="email">
                                <label for="email" class="label">Email</label>
                                    <div class="icon" @click="clearValue('email')">
                                        <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" fill="currentColor" class="bi bi-x-lg" viewBox="0 0 16 16">
                                            <path d="M2.146 2.854a.5.5 0 1 1 .708-.708L8 7.293l5.146-5.147a.5.5 0 0 1 .708.708L8.707 8l5.147 5.146a.5.5 0 0 1-.708.708L8 8.707l-5.146 5.147a.5.5 0 0 1-.708-.708L7.293 8z"/>
                                        </svg>
                                    </div>
                        </div>
                        <div class="password input-box">
                            <input :type="inputTypePass" placeholder="" id="pass" v-model="password">
                                <label for="pass" class="label">Password</label>
                                    <div class="icon" @click="clearValue('password')">
                                        <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" fill="currentColor" class="bi bi-x-lg" viewBox="0 0 16 16">
                                            <path d="M2.146 2.854a.5.5 0 1 1 .708-.708L8 7.293l5.146-5.147a.5.5 0 0 1 .708.708L8.707 8l5.147 5.146a.5.5 0 0 1-.708.708L8 8.707l-5.146 5.147a.5.5 0 0 1-.708-.708L7.293 8z"/>
                                        </svg>
                                    </div>
                                    <div class="icon-pass-vis" @click="isPassword = !isPassword">
                                        <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" fill="currentColor" class="bi bi-eye-fill" viewBox="0 0 16 16">
                                            <path d="M10.5 8a2.5 2.5 0 1 1-5 0 2.5 2.5 0 0 1 5 0"/>
                                            <path d="M0 8s3-5.5 8-5.5S16 8 16 8s-3 5.5-8 5.5S0 8 0 8m8 3.5a3.5 3.5 0 1 0 0-7 3.5 3.5 0 0 0 0 7"/>
                                        </svg>
                                    </div>
                        </div>
                        <div class="conf-password input-box">
                            <input type="password" placeholder="" id="conf-pass" v-model="confirm">
                                <label for="conf-pass" class="label">Confirm password</label>
                                    <div class="icon" @click="clearValue('confirm')">
                                        <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" fill="currentColor" class="bi bi-x-lg" viewBox="0 0 16 16">
                                            <path d="M2.146 2.854a.5.5 0 1 1 .708-.708L8 7.293l5.146-5.147a.5.5 0 0 1 .708.708L8.707 8l5.147 5.146a.5.5 0 0 1-.708.708L8 8.707l-5.146 5.147a.5.5 0 0 1-.708-.708L7.293 8z"/>
                                        </svg>
                                    </div>
                                    <div class="err-sec">
                                        <p class="error">{{ errorString }}</p>
                                    </div>
                        </div>
                    </div>
                        <div class="rem-block">
                            <input type="checkbox" id="rem">
                                <label for="rem" class="rem-label">Remember me</label>
                        </div>
                            <div class="button-container">
                                <button type="button" @click="sendData" @keyup.enter="sendData">CREATE</button>
                            </div>
                </div>
            </form>
        </div>
    </div>
  </footer>
</template>

<style scoped>

    footer {
        padding: 40px 10px 10px 10px;
        color: #cecece;
        font-family: 'Roboto', sans-serif;
        width: auto;
        height: max-content;
        background: rgb(53,80,150);
        background: linear-gradient(180deg, rgba(24, 52, 98, 0.717) 16%, rgba(0,10,30,1) 100%);
    }

    footer .header-text-block {
        text-align: center;
    }

    footer .header-text-block h2 {
        font-size: 18px;
        font-weight: 500;
    }

    footer .list-block {
        margin: 25px 0;
        padding: 0 40px;
        display: flex;
        flex-direction: row;
        align-items: center;
        justify-content: space-around;
    }

    footer .list-block h3 {
        font-size: 16px;
        font-weight: 400;
        color: rgb(123, 169, 255);
    }

    footer .list-block li, a {
        color: #cecece;
        display: flex;
        align-items: center;
        justify-content: flex-start;
        gap: 5px;
        text-decoration: none;
        transition: all .1s ease;
        cursor: pointer;
    }

    footer .list-block a:hover {
        color: hsl(216, 100%, 69%);
    }

    footer .list-block .account-block li:nth-child(1):hover {
        color: rgb(101, 255, 242);
    }

    footer .list-block .account-block li:nth-child(2):hover {
        color: rgb(97, 255, 165);
    }

    footer .list-block .account-block li:nth-child(3):hover {
        color: rgb(255, 202, 95);
    }

    footer .list-block ul {
        display: flex;
        flex-direction: column;
        row-gap: 10px;
        margin: 15px 0;
        list-style-type: none;
    }

    .footer-content .input-form-container {
        width: 100%;
        height: 100%;
        backdrop-filter: blur(20px);
        position: fixed;
        top: 0;
        left: 0;
        z-index: 9999;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .input-form-container form {
        width: 440px;
        height: 550px;
        background-color: #001a23c0;
        border-radius: 55px;
        border: 1px solid #00b3ff;
        padding: 10px;
        user-select: text;
        box-shadow: 0 0 75px #0091ff65;
    }

    .input-form-container form .form-wrapper {
        display: flex;
        flex-direction: column;
        align-items: center;
    }

    form .form-wrapper .logo-container {
        width: 105px;
        position: relative;
        top: -20px;
    }

    form .form-wrapper .logo-container img {
        width: 100%;
        filter: drop-shadow(2px 2px 15px #000);
    }

    form .form-wrapper .heading-block h2 {
        font-size: 26px;
        font-family: 'Poppins', sans-serif;
        letter-spacing: 5px;
        text-shadow: 2px 2px 15px #000;
        color: #c7e6ff;
    }

    .form-wrapper .inputs-container {
        width: 330px;
        display: flex;
        flex-direction: column;
        justify-content: center;
        row-gap: 25px;
        margin: 30px 0;
    }

    .form-wrapper .inputs-container .input-box {
        position: relative;
    }

    .form-wrapper .inputs-container input {
        box-sizing: border-box;
        width: 100%;
        outline: none;
        border: none;
        padding: 10px 15px;
        border-radius: 20px;
        background-color: transparent;
        border: 2px solid #00b3ff;
        transition: all 0.2s ease;
        color: #dadada;
        font-family: 'Poppins', sans-serif;
        font-weight: 500;
        cursor: pointer;
    }

    .inputs-container input:focus {
        border-color: hsl(162, 100%, 80%);
        filter: drop-shadow(0 0 10px rgb(0, 255, 166));
        cursor: text;
    }

    .inputs-container .input-box input:focus + .label,
    input:not(:placeholder-shown) + .label {
        background-color: rgb(0, 255, 174);
        transform: translateY(-20px);
    }

    .inputs-container .input-box label {
        background-color: #008ecaed;
        font-family: 'Poppins', sans-serif;
        font-size: 13px;
        font-weight: 600;
        padding: 0 8px;
        border-radius: 15px;
        cursor: pointer;
        position: absolute;
        transition: all 0.4s ease;
        top: 25%;
        left: 10px;
        color: #fff;
        font-style: italic;
    }

    .inputs-container .input-box .icon {
        position: absolute;
        top: 30%;
        right: 10px;
        cursor: pointer;
    }

    .inputs-container .input-box .icon-pass-vis {
        position: absolute;
        top: 30%;
        right: 35px;
        cursor: pointer;
        transition: all 0.2s ease;
    }

    .inputs-container .input-box .icon-pass-vis:hover {
        color: rgb(255, 255, 255);
    }

    .inputs-container .input-box .err-sec {
        font-size: 14px;
        font-weight: default;
        color: red;
        padding-left: 10px;
        padding-top: 10px;
        position: absolute;
        left: 0;
        font-style: italic;
    }

    form .form-wrapper .rem-block {
        width: 100%;
        text-align: center;
    }

    form .form-wrapper .rem-block input {
        margin-right: 5px;
        cursor: pointer;
    }
    
    form .form-wrapper .rem-block label {
        font-family: 'Poppins', sans-serif;
        font-weight: 600;
        color: #fff;
    }

    .form-wrapper .button-container button {
        padding: 15px 100px;
        margin: 20px 0;
        border: none;
        cursor: pointer;
        border-radius: 20px;
        background: linear-gradient(230deg, rgb(0, 187, 255), rgb(0, 64, 128));
        color: #fff;
        font-size: 16px;
        font-weight: 600;
        box-shadow: 5px 5px 20px #00000068;
        letter-spacing: 3px;
        font-style: italic;
        transition: filter 0.2s ease;
    }

    .form-wrapper .button-container button:hover {
        filter: brightness(80%);
    }

    @media (max-width: 480px) {
        footer .list-block {
            padding: 5px;
        }
    }

</style>

<script>
export default {
    data() {
        return {
            activeLogin: null,
            email: '',
            password: '',
            confirm: '',
            errorString: '',
            isPassword: true,
        }
    },
    methods: {
        activeProfileAdd(n) {
            this.activeLogin = n;
        },
        clearValue(value) {
            if (this[value] == 0) {
                this.errorString = `Field ${value} is empty`
            } else {
                this[value] = '';
                    this.errorString = ''
            }
        },
        sendData() {
            if (this.email == '') {
                this.errorString = 'Email not entered';
            } else if (this.password == '') { 
                this.errorString = 'Password not entered'
            } else if (this.confirm == '') {
                this.errorString = 'Password not confirmed'
            } else if (this.password !== this.confirm) {
                this.errorString = 'Password mismatch'
            } else {
                this.errorString = '';
            }
        }
    },
    computed: {
        inputTypePass() {
             return this.isPassword ? 'password' : 'text'
        }
    }
}
</script>