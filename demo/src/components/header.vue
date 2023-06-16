<script setup>
import { ref, computed, onMounted } from 'vue';
// router-link 連結
const goTo = (getPlace) => {
    let placeID = document.querySelector(getPlace)
    if (placeID == null) {
        setTimeout(() => {
            document.querySelector(getPlace).scrollIntoView({ behavior: 'smooth' })
        }, 300)
    } else {
        placeID.scrollIntoView({ behavior: 'smooth' })
    }
}
// top鍵滾動才出現
const topShow = ref(false)
const gotop = () => {
    if (scrollY >= 50) {
        topShow.value = true;
    } else {
        topShow.value = false;
    }
}
onMounted(() => {
    window.addEventListener("scroll", gotop)
})


// RWD
const check = ref(false)
</script>

<template>
    <header>
        <router-link to="/">
            <img src="../img/header-logo.png" class="logo" alt="">神兵資訊科技服務股份有限公司
        </router-link>
        <!-- 漢堡叉叉按鈕 + nav 選單 -->
        <label>
            <div class="hamburger">
                <input type="checkbox" id="switch" @click="check = !check" :checked="check">
                <div class="line line-1"></div>
                <div class="line line-3"></div>
                <nav class="menu" :class="{ active: check }">
                    <ul>
                        <li><router-link to="/" @click="check = false, goTo('body')">首頁</router-link></li>
                        <li><router-link to="/about" @click="check = false, goTo('body')">關於我們</router-link></li>
                        <li>
                            <router-link to="/" @click="goTo('.main-main'), check = false">服務項目</router-link>
                        </li>
                        <li>
                            <router-link to="" @click="check = false, goTo('footer')">聯絡我們</router-link>
                        </li>
                        <!-- <li><a href="#main-main">服務項目</a></li> -->
                        <!-- <li><a href="Form">聯絡我們</a></li> -->
                    </ul>
                    <div class="social-item1">
                        <router-link to="#"><img src="../img/header-fb.png" alt=""></router-link>
                        <router-link to="#"><img src="../img/header-whatsapp.png" alt=""></router-link>
                        <router-link to="#"><img src="../img/header-linkedin.png" alt=""></router-link>
                    </div>
                </nav>
                <div class="Shady">
                </div>
            </div>
            <div class="top" v-show="topShow" @click="goTo('body'), check = !check">Top</div>
        </label>
    </header>
</template>

<style scoped>
* {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
}

header {
    height: 100px;
    display: flex;
    align-items: center;
}

header .logo {
    width: 90px;
    font-size: 0px;
    margin-left: 20px;
}

header a {
    display: flex;
    justify-content: center;
    align-items: center;
    margin-left: 30px;
    color: rgb(8, 15, 53);
    text-decoration: none;
    font-size: 20px;
}

/* ----------------------- */

.menu {
    position: absolute;
    top: 40px;
    right: 0;
}

.menu ul {
    display: flex;
    text-decoration: none;
    margin-left: 100px;
    overflow: hidden;
}

.menu ul li {
    list-style-type: none;
    margin-right: 10px;
    /* background-color: #fff; */

}

.menu ul li a {
    text-decoration: none;
    font-size: large;
    color: black;
    margin-right: 30px;
    letter-spacing: 2px;
    cursor: pointer;
}

.menu ul li a:hover {
    color: rgb(158, 0, 0);
}

.social-item1 {
    position: fixed;
    z-index: 99;
    top: 45%;
    right: 50px;
}

.social-item1 a {
    margin-bottom: 30px;
}

label .hamburger #switch {
    display: none;
}

.top {
    position: fixed;
    z-index: 99;
    bottom: 5%;
    right: 30px;
    padding: 15px;
    background-color: #0E2870;
    color: #fff;
    border-radius: 10px;
    cursor: pointer;
}

.top:hover {
    background-color: rgb(97, 97, 97);
}


@media (min-width:912px) and (max-width:1280px) {
    header {
        height: 100px;
    }

    header .logo {
        width: 90px;
        font-size: 0px;
        margin-left: 20px;
    }

    header .logo a {
        color: rgb(8, 15, 53);
        text-decoration: none;
        font-size: 20px;
    }

}

@media (min-width:768px) and (max-width:911px) {
    header .logo {
        width: 90px;
        font-size: 0px;
        margin-left: 20px;
    }

    header .logo a {
        color: rgb(8, 15, 53);
        text-decoration: none;
        font-size: 18px;
    }
}

@media (min-width: 555px) and (max-width: 767px) {
    header {
        height: 100px;
    }

    header .logo {
        width: 80px;
        font-size: 0px;
        margin-left: 10px;
    }

    header a {
        color: rgb(8, 15, 53);
        text-decoration: none;
    }
}

@media (max-width: 554px) {
    header .logo {
        width: 80px;
        margin-left: 10px;
    }

    header a {
        font-size: 15px;
    }

}

@media (max-width: 410px) {
    header .logo {
        width: 50px;
        margin-left: 5px;
    }

    header a {
        font-size: 14px;
        margin-left: 3px;
    }
}

@media (max-width: 944px) {
    label {
        float: left;
    }

    label .hamburger {
        width: 30px;
        height: 30px;
        position: fixed;
        background-color: unset;
        right: 20px;
        top: 20px;
        z-index: 10;
        cursor: pointer;
        margin-top: 10px;
    }

    label .hamburger #switch {
        display: none;
    }

    /* 叉叉變hamburger */
    label .hamburger .line {
        position: absolute;
        width: 30px;
        height: 5px;
        background-color: #FAC068;
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%);
        z-index: 20;
        transition-property: top, transform;
        transition-duration: 0.5s, 0.1s;
        box-shadow: 2px 2px;
    }

    label .hamburger .line-1 {
        top: 25%;
    }

    label .hamburger .line-3 {
        top: 75%;
    }

    /* hamburger變叉叉 */
    label .hamburger #switch:checked~.line {
        transition-duration: 0.1s, 0.5s;
        box-shadow: unset;
    }

    label .hamburger #switch:checked~.line-1 {
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%) rotate(-45deg);
    }

    label .hamburger #switch:checked~.line-3 {
        top: 50%;
        left: 50%;
        transform: translate(-50%, -50%) rotate(45deg);
    }

    label .hamburger #switch:checked~.Shady {
        position: fixed;
        z-index: -10;
        width: 100%;
        top: 0px;
        right: 0;
        height: 100vh;
        background-color: rgba(0, 0, 0, 0.596);
        opacity: 0.8;
        transition: 0.5s;
        display: block;
    }

    label .hamburger .Shady {
        opacity: 0;
    }

    nav {
        display: flex;
        flex-direction: column;
        justify-content: center;
        align-items: center;
        width: 0px;
        height: 110vh;
        margin: -70px -70px 0 0;
        background-color: rgba(255, 255, 255, 0.932);
        overflow: hidden;
        transition: 1s;
    }

    .active {
        width: 500px;
    }

    label .hamburger nav ul {
        display: flex;
        flex-direction: column;
        padding: 0;
        list-style-type: none;
        width: 300px;
        text-align: center;
        margin: -80px 0 0 -10px;

    }

    label .hamburger nav ul a,
    label .hamburger nav ul div {
        text-decoration: none;
        text-align: center;
        font-size: 25px;
        font-weight: bold;
        letter-spacing: 0.5em;
        display: block;
        padding: 20px;
        padding-right: 10px;
        color: rgb(9, 9, 83);
    }

    label .hamburger nav ul div {
        margin-left: 30px;
    }

    .social-item1 {
        position: unset;
        display: flex;
        margin: 20px 0 0 -45px;
    }

}

@media (max-width: 600px) {
    label .hamburger #switch:checked~nav {
        width: 360px;
    }
}
</style>