<script setup>
import BaseButtonVue from './components/BaseButton.vue'
import BaseIcon from './components/BaseIcon.vue';

const clickButton = () => {
  console.log('click')
}

const clickTimerButton = () => {
  console.log('click timer')
}

  // data() {
  //   return {
  //     currentTime: 0,
  //     timer: null,
  //     color: 'primary'
  //   }
  // },
  // methods: {
  //   clickBtn() {
  //     console.log('click')
  //   },
  //   restartTimer() {
  //     console.log('start');
  //     clearTimeout(this.timer);
  //     this.currentTime = 15;
  //     this.color = 'disabled';
  //     this.timer = setInterval(() => {
  //       this.currentTime--
  //     }, 1000)
  //   },
  //   stopTimer() {
  //     clearTimeout(this.timer)
  //   },
  // },
  // watch: {
  //   currentTime(time) {
  //     if (time <= 0) {
  //       console.log('stop');
  //       this.stopTimer();
  //       this.color = 'primary'
  //     }
  //   }
  // }
</script>

<template>
  <div class="container">
    <h1>This is Vue3-button-component demonstration</h1>
    <div class="content">
      <div class="content__wrapper">
        <h2 class="content__title">(button-classic)</h2>
        <h2 class="content__btn-title">(primary)</h2>
        <BaseButtonVue @click="clickButton" color="primary">Отправить&nbsp;письмо</BaseButtonVue>
        <h2 class="content__btn-title">(secondary)</h2>
        <BaseButtonVue @click="clickButton" color="secondary">Отправить&nbsp;письмо</BaseButtonVue>
        <h2 class="content__btn-title">(warning)</h2>
        <BaseButtonVue @click="clickButton" color="warning">Отправить&nbsp;письмо</BaseButtonVue>
        <h2 class="content__btn-title">(disabled)</h2>
        <BaseButtonVue @click="clickButton" :disabled="true">Отправить&nbsp;письмо</BaseButtonVue>
        <h2 class="content__btn-title">(info)</h2>
        <BaseButtonVue @click="clickButton" color="info">Отправить&nbsp;письмо</BaseButtonVue>
        <h2 class="content__btn-title">(danger)</h2>
        <BaseButtonVue @click="clickButton" color="danger">Отправить&nbsp;письмо</BaseButtonVue>
        <h2 class="content__btn-title">(action)</h2>
        <BaseButtonVue @click="clickButton" color="action">Отправить&nbsp;письмо</BaseButtonVue>
      </div>
      <div class="content__wrapper">
        <h2 class="content__title">(button multi-sized)</h2>
        <div class="content__btn-group">
          <BaseButtonVue type="icon" color="primary" size="small">
            <BaseIcon name="arrow1" size="small"></BaseIcon>
          </BaseButtonVue>
          <BaseButtonVue type="icon" color="primary">
            <BaseIcon name="arrow1"></BaseIcon>
          </BaseButtonVue>
        </div>
        <div class="content__btn-group">
          <BaseButtonVue type="icon" color="danger" size="small">
            <BaseIcon name="exit" size="small" viewBox="0 0 37 37"></BaseIcon>
          </BaseButtonVue>
          <BaseButtonVue type="icon" color="danger">
            <BaseIcon name="exit" width="37" height="37" viewBox="0 0 37 37"></BaseIcon>
          </BaseButtonVue>
        </div>
        <div class="content__btn-group">
          <BaseButtonVue type="icon" color="info" size="small">
            <BaseIcon name="quest" size="small"></BaseIcon>
          </BaseButtonVue>
          <BaseButtonVue type="icon" color="info">
            <BaseIcon name="quest"></BaseIcon>
          </BaseButtonVue>
        </div>
        <div class="content__btn-group">
          <BaseButtonVue type="icon" color="primary" size="small">
            <BaseIcon name="arrow" size="small"></BaseIcon>
          </BaseButtonVue>
          <BaseButtonVue type="icon" color="primary">
            <BaseIcon name="arrow"></BaseIcon>
          </BaseButtonVue>
        </div>
        <div class="content__btn-group">
          <BaseButtonVue type="icon" color="danger" size="small">
            <BaseIcon name="google" size="small"></BaseIcon>
          </BaseButtonVue>
          <BaseButtonVue type="icon" color="danger">
            <BaseIcon name="google"></BaseIcon>
          </BaseButtonVue>
        </div>
        <div class="content__btn-group">
          <BaseButtonVue type="icon" color="info" size="small">
            <BaseIcon name="vk" size="small"></BaseIcon>
          </BaseButtonVue>
          <BaseButtonVue type="icon" color="info">
            <BaseIcon name="vk"></BaseIcon>
          </BaseButtonVue>
        </div>
        <div class="content__btn-group">
          <BaseButtonVue type="icon" color="action" size="small">
            <BaseIcon name="class" size="small"></BaseIcon>
          </BaseButtonVue>
          <BaseButtonVue type="icon" color="action">
            <BaseIcon name="class"></BaseIcon>
          </BaseButtonVue>
        </div>
        <div class="content__btn-group">
          <BaseButtonVue type="icon" color="primary" size="small">
            <BaseIcon name="pen" size="small" viewBox="0 0 42 42"></BaseIcon>
          </BaseButtonVue>
          <BaseButtonVue type="icon" color="primary">
            <BaseIcon name="pen" width="42" height="42" viewBox="0 0 42 42"></BaseIcon>
          </BaseButtonVue>
        </div>
      </div>
      <div class="content__wrapper">
        <h2 class="content__title">(button link)</h2>
        <BaseButtonVue href="#" type="link">Напомнить PIN-код</BaseButtonVue>
      </div>
      <div class="content__wrapper">
        <h2 class="content__title">(button timer)</h2>
        <BaseButtonVue @click="clickTimerButton" type="timer">повторное&nbsp;письмо</BaseButtonVue>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
@import "@/styles/global.scss";

#app {
  max-width: 1400px;
  margin: 0 auto;
  padding: 2rem;
  text-align: center;
  font-family: Phoshate, Helvetica, Arial, sans-serif;
  font-size: 16px;
  line-height: 24px;
  font-weight: 400;
}

.content {
  display: flex;
  flex-direction: column;
  align-items: center;

  &__wrapper {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    margin-bottom: 20px;
  }

  &__title {
    align-self: center;
    font-weight: 400;
    font-size: 18px;
    line-height: 24px;
  }

  &__btn-title {
    margin-top: 0;
    margin-bottom: 8px;
    font-weight: 400;
    font-size: 18px;
    line-height: 24px;
    color: #fff;
  }

  &__btn-group {
    display: flex;
    justify-content: space-between;
    width: 100%;
    margin-bottom: 24px;
  }

  .button_button {
    margin-bottom: 24px;
  }
}
</style>
