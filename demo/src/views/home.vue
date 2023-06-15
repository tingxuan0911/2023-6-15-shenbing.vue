<script setup>

</script>

<template>
  <main>
    <div class="main-head">
      <div class="head-img"></div>
      <div>
        <h2>關於神兵資訊</h2>
        <div>
          <h3>____</h3>
          <p>神兵資訊放眼全球，展望科技新趨勢，多方部屬在台灣與馬來西亞媒合各類資源，同時廣納各界專業人才、致力推廣國際合作，提供金融科技、遊戲及跨國電商等相關整合服務！</p>
        </div>
        <router-link to="/about">
          <p>+ Find out more</p>
        </router-link>
      </div>
    </div>
    <!-- ------------------------------- -->
    <div class="main-main">
      <div>
        <h2>服務項目</h2>
        <p>我們提供軟硬體設計及開發服務、伺服器架設、伺服器租賃服務、金融科技技術支援、遊戲媒合、遊戲對接等相關服務。</p>
      </div>
      <div class="row">
        <div class="col">
          <h4>軟硬體開發</h4>
          <p>神兵擁有經驗豐富的系統開發團隊，藉由完善的產品開發與QA流程，能針對需求方之需求規畫所需的功能並進行技術開發及後續驗收。 此外，也提供硬體採購、改良服務，軟硬體需求幫您一次到位。</p>
        </div>
        <div class="col">
          <h4>伺服器建設</h4>
          <p>我們提供伺服器建設與租賃服務，支援MYSQL資料庫、DNS域名、VPN虛據私人、EMAIL電子郵件等伺服器之建置與維護。</p>
        </div>
        <div class="col">
          <h4>國際資源媒合</h4>
          <p>布局全球，展望跨境市場！神兵目前已與馬來西亞當地新創電商平台簽約合作，同時也有不同類型的合作項目，如：遊戲、金流商等接洽中。未來也將持續擴展，不同國家的合作機會，以期達到跨境無國界的合作模式。</p>
        </div>
        <div class="col">
          <h4>遊戲資源</h4>
          <p>我們設有遊戲專職單位，主要業務為遊戲IP價值評估，經過評估後，會將具市場潛力的遊戲IP進行遊戲收購、測試、再開發與串接等業務。</p>
        </div>
        <div class="col">
          <h4>區塊鏈技術服務</h4>
          <p>神兵資訊提供高效率、客製化的FinTech應用串接方案，透過經驗豐富的金融系統研發團隊，開發出多項相金融科技關項目， 如：虛擬貨幣交易所、中心化錢包等。</p>
        </div>
        <div class="col">
          <h4>網站架站</h4>
          <p>不論是一般品牌網站或電子商務網站，神兵提供客製化網站架站服務，從設計到架站、金物流串接、會員系統等一條龍建置方案。</p>
        </div>
      </div>
    </div>
    <div class="main-footer">
      <h2>放眼全球 多點布局</h2>
      <p>近年來金融科技的應用越發盛行，貨幣交易的應用已經延伸至跨境電商，未領先同業，我們將多點布局各種面向，自不同產業至其使用深度，縱橫開拓金融科技的應用。
      </p>
    </div>
  </main>
</template>

<style scoped>
* {
  box-sizing: border-box;
}

/* main-head */
.main-head {
  position: relative;
  margin-bottom: 280px;
  width: 100%;
}

.head-img {
  width: 85%;
  height: 534px;
  background-image: url('../img/main-head.webp');
  background-position: center;
}

.main-head>div:nth-child(2) {
  position: absolute;
  right: 32%;
  bottom: -35%;
  width: 600px;
  height: 350px;
  padding: 60px;
  background-color: rgb(245, 245, 245);
}

h2 {
  font-size: 38px;
}

.main-head>div>div {
  display: flex;
}

.main-head>div>div>h3 {
  font-size: 28px;
}

.main-head>div>div>p {
  margin-top: 18px;
  margin-left: 20px;
  line-height: 40px;
  font-size: 15px;
}

.main-head>div>a:last-child {
  position: absolute;
  bottom: -7%;
  right: 13%;
  width: 130px;
  padding: 15px 12px;
  background-color: #DC3545;
  border-radius: 3px;
}

.main-head>div>a:last-child>p {
  margin: 0;
  color: rgb(255, 255, 255);
}

/* main-main */
.main-main>div:first-child {
  padding: 80px 10%;
  height: 360px;
  background-color: #0E2870;
  color: #fff;
}

.row {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 5%;
  margin: 0 15%;
  margin-top: -10%;
}

.col {
  position: relative;
  margin-bottom: 50px;
  width: 28%;
  background-color: rgb(248, 248, 248);
  box-shadow: 13px 13px 0px 0px #ffffff5d, 8px 8px 5px 0px rgba(240, 240, 240, 0.836);
}

.col h4 {
  margin: 50px 0 20px 0;
  font-size: 24px;
  text-align: center;
}

.col p {
  margin: 20px 30px;
  font-size: 15px;
  color: rgb(136, 136, 136);
}

/* main-footer */
.main-footer {
  position: relative;
  width: 100%;
  height: 460px;
  background-image: url('../img/main-footer.webp');
}

.main-footer::after {
  content: '';
  display: block;
  position: absolute;
  top: 0;
  width: 100%;
  height: 460px;
  background-color: rgba(0, 0, 0, 0.411);
}

.main-footer>h2,
.main-footer>p {
  position: absolute;
  right: 50%;
  transform: translateX(50%);
  z-index: 99;
  color: #fff;
}

.main-footer>h2 {
  top: 80px;
}

.main-footer>p {
  top: 180px;
  width: 60%;
  font-size: 26px;
}

@media (max-width: 1280px) {
  .main-head>div:nth-child(2) {
    right: 13%;
  }
}

@media (max-width: 1200px) {
  .head-img {
    width: 100%;
  }
}

@media (max-width: 970px) {
  .col {
    width: 40%;
  }
}

@media (max-width: 910px) {
  .main-head {
    margin-bottom: 0px;
  }

  .main-head>div:nth-child(2) {
    position: unset;
    width: 100%;
    background-color: #fff;
  }

  .main-head>div>a:last-child {
    bottom: 50px;
    right: 70px;
    background-color: unset;
  }

  .main-head>div>a:last-child>p {
    /* margin-top: -120px; */
    color: #DC3545;
    text-decoration: underline;
  }

  .main-main>div:first-child {
    padding: 45px 5%;
    height: inherit;
    line-height: 50px;
  }

  .row {
    display: flex;
    flex-direction: column;
    width: 100%;
    margin: 0;
  }

  .col {
    margin-bottom: 20px;
    width: 100%;
    background-color: rgb(236, 236, 236);
    box-shadow: unset;
  }

  .col h4 {
    margin: 20px;
    font-size: 20px;
    font-weight: bolder;
    text-align: left;
  }

  .col p {
    margin: 0px 20px 20px 20px;
    font-size: 14px;
    color: rgb(71, 71, 71);
  }

  .main-footer {
    margin-top: -20px;
  }

  @media (max-width: 645px) {
    .main-head>div:nth-child(2) {
      height: inherit;
      padding: 40px 20px;
    }

    .main-head>div>a:last-child {
      bottom: 0px;
      right: 20px;
    }

    .main-footer>h2 {
      width: 100%;
      text-align: center;
      font-size: 30px;
    }

    .main-footer>p {
      top: 160px;
      width: 80%;
      font-size: 22px;
      line-height: 40px;
    }
  }




}
</style>
