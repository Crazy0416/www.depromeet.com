<template>
<div class="contact-container">
  <div class="container">
    <h1 class="contact-title"><b>Thank you,</b></h1>
    <h1 class="contact-content">
      더 자세한 디프만 활동은<br>
      <b @click="goToMedium()">미디엄</b>, <b @click="goToFacebook()">페이스북</b>을 확인해 주세요.
    </h1>

    <div class="contact-items">
      <div class="contact-item">
        <kakao />
      </div>
      <div class="contact-item" @click="goToFacebook()">
        <facebook />
      </div>
      <div class="contact-item">
        <email />
      </div>
      <div class="contact-item" @click="goToInstagram()">
        <instagram />
      </div>
    </div>
  </div>
</div>
</template>

<script lang="ts">
import { Component, Vue } from 'vue-property-decorator';
import Kakao from '@/assets/ico-kakao.svg';
import Facebook from '@/assets/ico-facebook.svg';
import Email from '@/assets/ico-mail.svg';
import Instagram from '@/assets/ico-instagram.svg';

@Component({
  components: {
    Kakao,
    Facebook,
    Email,
    Instagram,
  },
})
export default class Contact extends Vue {
  goToMedium = () => window.open('https://medium.com/@depromeet', '_blank');

  goToInstagram = () => window.open('https://www.instagram.com/depromeet/', '_blank');

  goToFacebook = () => window.open('https://www.facebook.com/depromeet', '_blank');
}
</script>

<style lang="scss" scoped>
.contact-container {
  height: 370px;
  background-color: #222222;

  .container {
    height: 100%;
    padding-top: 54px;
    padding-bottom: 63px;
  }

  h1 {
    font-size: 30px;
    font-weight: 300;
    font-style: normal;
    font-stretch: normal;
    letter-spacing: -0.9px;
    text-align: center;
    color: #ffffff;

    b {
      font-weight: 900;
      cursor: pointer;
    }
  }

  .contact-title {
    margin-bottom: 13px;
  }

  .contact-content {
    margin-bottom: 40px;
  }

  .contact-items {
    display: flex;
    flex-direction: row;
    justify-content: center;
    align-items: center;

    .contact-item {
      width: 70px;
      height: 70px;
      border-radius: 50%;
      background-color: #ffffff;
      cursor: pointer;
      display: flex;
      justify-content: center;
      align-items: center;

      &:not(:last-child) {
        margin-right: 30px;
      }
    }
  }
}
</style>
