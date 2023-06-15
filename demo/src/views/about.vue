<script setup>

</script>

<template>
  <main>
    <div class="main-head">
      <div class="head-img"></div>
      <div>
        <h2>關於我們</h2>
      </div>
      <p>由於疫情導致消費者習慣的改變，實體銀行逐漸轉型至網路銀行、線上的消費行為也大幅上升。網路銀行提供了更好的客戶體驗，更快、更高效率的服務。</p>
      <p>根據Statista，2021年有64.6%的美國公民使用網路銀行，意味著網路銀行將成為金融領域的轉型工具。據此，有專家預估金融科技規模預計將從2020年的30億美元增加到2025年的397億美元。</p>
      <p>但國內市場上，金融科技方面的技術與資源仍較為匱乏，為提供金融科技產業具備發展的動能，使之有效地進行，神兵結合本身跨國資源與區塊鏈技術，給需求方區塊鏈功能開發服務，同時更能整併資源提供跨國串接，讓需求方點線面一次到位。</p>
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
  /* margin-bottom: 280px; */
  width: 100%;
}

.head-img {
  width: 85%;
  height: 534px;
  background-image: url('../img/about-bgi.jpg');
  background-position: center;
}

.main-head>div:nth-child(2) {
  position: absolute;
  right: 24%;
  top: 450px;
  width: 680px;
  padding: 45px;
  background-color: rgb(245, 245, 245);
}

h2 {
  font-size: 60px;
  color: #0E2870;
}

p {
  margin: 50px auto;
  width: 55%;
  font-size: 15px;
  line-height: 30px;
}

p:nth-child(3) {
  margin-top: 180px;
}


@media (max-width: 1200px) {
  .head-img {
    width: 100%;
  }

  .main-head>div:nth-child(2) {
    right: 13vw;
    top: 450px;
  }
}

@media (max-width: 800px) {
  .main-head>div:nth-child(2) {
    right: 24%;
    padding: 40px;
    width: 350px;
  }

  h2 {
    font-size: 50px;
  }

  @media (max-width: 500px) {
    .main-head>div:nth-child(2) {
      position: unset;
      width: 100%;
      background-color: #fff;
    }

    p:nth-child(3) {
      margin-top: 10px;
    }
  }
}



/* @media (max-width: 910px) {
  .main-head {
    margin-bottom: 0px;
  }

  .main-head>div:nth-child(2) {
    position: unset;
    width: 100%;
    background-color: #fff;
  } */

/* @media (max-width: 645px) {
  .main-head>div:nth-child(2) {
    height: inherit;
    padding: 40px 20px;
  } */


/* } */</style>
