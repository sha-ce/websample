<template>
  <div>
    <Header/>
    <Menu/>
    <div class="contact">
      <div class="contact-title">
        お問い合わせ
      </div>
      <div class="contact-form-wrap">
        <div class="contact-form">
          <div class="contact-form-text">
            お名前
          </div>
          <div class="contact-form-input">
            <input id="name" type="text"/>
          </div>
        </div>
        <div class="contact-form">
          <div class="contact-form-text">
            メールアドレス
          </div>
          <div class="contact-form-input">
            <input id="email" type="email"/>
          </div>
        </div>
        <div class="contact-form">
          <div class="contact-form-text">
            お問い合わせ内容
          </div>
          <div class="contact-form-input message">
            <textarea id="message"/>
          </div>
        </div>
        <div class="contact-form-post">
          <button>送信</button>
        </div>
      </div>
    </div>
    <Footer/>
  </div>
</template>

<script>
import Header from '../../components/Header.vue';
import Menu from '../../components/Menu.vue';
import Footer from '../../components/Footer.vue';

export default {
  components: { Header, Menu, Footer },
}
</script>

<style>
html, body {
  margin: 0;
  padding: 0;
}
</style>

<style scoped>
*:focus {
  outline: none;
}
.contact {
  background: white;
  font-family: 'Inter', '游ゴシック';
  justify-content: center;
  padding-top: 100px;
}
.contact-title {
  font-size: 100px;
  color: gray;
  margin: 0 0 50px 100px;
}
.contact-form-wrap {
  width: 65%;
  text-align: center;
  margin: 30px auto;
}
.contact-form {
  margin: 30px 0;
}
.contact-form-text {
  width: 100%;
  font-size: 40px;
  color: gray;
  text-align: left;
}
.contact-form-input {
  width: 100%;
  text-align: center;
}
.contact-form-input input
,.contact-form-input textarea {
  width: 100%;
  background: #eeeeee;
  border: none;
  border-radius: 8px;
  font-size: 40px;
  color: gray;
  padding: 10px 20px;
}
.contact-form-input input:focus
,.contact-form-input textarea:focus {
  outline: solid 1px gray;
}
.message textarea {
  resize: none;
  height: 300px;
  text-align: initial;
  white-space: normal;
}
.contact-form-post {
  text-align: center;
}
.contact-form-post button{
  font-size: 40px;
  color: gray;
  background: transparent;
  border: solid 2px gray;
  border-radius: 8px;
  cursor: pointer;
  padding: 5px 50px;
}
.contact-form-post button:hover{
  color: white;
  background: gray;
  transition: 0.3s ease;
}
</style>
