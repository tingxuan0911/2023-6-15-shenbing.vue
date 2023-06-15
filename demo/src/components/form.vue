<script setup>
import axios from 'axios';
import { ref, onMounted, reactive } from 'vue';

// input name 定義
const form = reactive({
  name: '',
  mail: '',
  title: '',
  msg: ''
})

// 清空 input
const inputClean = () => {
  form.name = '',
    form.mail = '',
    form.title = '',
    form.msg = ''
}

//傳送完成後顯示 .sendOK 3秒
const showSendOK = ref(false)
const showThank = () => {
  showSendOK.value = true
  setTimeout(() => {
    showSendOK.value = false
  }, 3000)
}

// btn可點擊
const isDisabled = ref(false) //disable屬性為false

// axios
const send = () => {
  isDisabled.value = true //disable屬性為true，.disabled css 先變灰色
  axios.post('http://192.168.66.17:81/sendEmail/', form)//與<form>連結
    .then(res => {
      console.log(res.data)
      if (res.data.code) {
        alert('傳送完成');
        inputClean()// 清空 input
        showThank()// 顯示 .sendOK 3秒
      } else if (res.data.message) {
        alert(res.data.message)
      } else {
        alert(res.data.msg)
      }
      isDisabled.value = false //disable屬性為false，alert按掉後.disabled css變回unset
    })
    .catch(error => {
      console.log(error);
    })
}
</script>

<template>
  <footer>
    <h2>聯絡我們</h2>
    <form @submit.prevent="send"><!-- 點擊按鈕submit後，跑send();使用.prevent畫面不會重新載入 -->
      <div>
        <label>姓名*<br>
          <input type="text" name="name" v-model="form.name"><!-- form表單的name用v-model綁定key -->
        </label>
        <label>信箱*<br>
          <input type="email" name="mail" v-model="form.mail">
        </label>
      </div>
      <label>標題*<br>
        <input type="text" name="title" v-model="form.title">
      </label>
      <label>留言<br>
        <textarea id="" name="msg" cols="30" rows="10" v-model="form.msg"></textarea>
      </label>
      <button type="submit" @click="send()" :disabled="isDisabled">送出</button><!-- disabled:button禁用語法 -->
      <p class="sendOK" v-if="showSendOK">感謝您!我們將盡快與您聯繫!</p>
    </form>
    <div class="info">
      <p>台中市西屯區台灣大道二段633號11樓之3</p>
      <p>Tel. 04-23293333</p>
      <p>Email. Service@shenbingtech.com</p>
    </div>
    <div class="copy">copyright © 2022 Shenbing All Rights Reserved.</div>
  </footer>
</template>

<style scoped>
footer {
  padding: 80px;
  width: 100%;
  background-color: #0E2870;
  color: #fff;
}

h2 {
  margin-bottom: 50px;
  text-align: center;
  font-size: 40px;
}

form {
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  gap: 20px;
  width: 100%;
}

form>div {
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 30px;
  width: 80%;
}

label {
  width: 80%;
  margin: 0 auto;
}

input,
textarea {
  width: 100%;
  height: 35px;
  background-color: unset;
  border: unset;
  border-bottom: 1px solid #fff;
  color: #fff;
  resize: vertical; /* 鎖textarea左右寬度 */
}

input:hover,
textarea:hover {
  border: 1px solid #fff;
}

input:focus,
textarea:focus {
  color: #333;
  background-color: #fff;
  border: 3px solid #1d44b1;
  outline: none;
}

textarea {
  height: 100px;
}

button {
  padding: 8px 40px;
  font-size: 20px;
  color: #fff;
  background-color: unset;
  border: unset;
}

button:hover {
  background-color: rgb(190, 1, 1);
}

/* 按鈕無法按時的CSS */
button:disabled {
  background-color: gray;
}

button:focus {
  border: 3px solid #1d44b1;
}

.sendOK {
  color: aqua;
  font-size: 24px;
}

.info {
  display: flex;
  justify-content: center;
  gap: 10%;
  margin: 50px 0;
}

.copy {
  margin: 20px 0;
  text-align: center;
}

@media(max-width:580px) {
  form>div {
    flex-direction: column;
    gap: 20px;
    width: 100%;
  }

  .info {
    flex-direction: column;
    gap: 15px;
  }
}
</style>
