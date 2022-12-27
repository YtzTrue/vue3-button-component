<script>
import BaseButtonVue from './components/BaseButton.vue'

export default {
  name: 'app',
  components: { BaseButtonVue },
  data() {
    return {
      currentTime: 0,
      timer: null,
      color: 'primary'
    }
  },
  methods: {
    clickBtn() {
      console.log('click')
    },
    restartTimer() {
      console.log('start');
      clearTimeout(this.timer);
      this.currentTime = 15;
      this.color = 'disabled';
      this.timer = setInterval(() => {
        this.currentTime--
      }, 1000)
    },
    stopTimer() {
      clearTimeout(this.timer)
    },
  },
  watch: {
    currentTime(time) {
      if (time <= 0) {
        console.log('stop');
        this.stopTimer();
        this.color = 'primary'
      }
    }
  }
}
</script>

<template>
  <div class="container">
    <h1>This is Vue3-button-component demonstration</h1>
    <div class="content">
      <div class="content__wrapper">
        <h2 class="content__title">(button-classic)</h2>
        <h2 class="content__btn-title">(primary)</h2>
        <BaseButtonVue class="content__btn" label="Отправить&nbsp;письмо" color="primary" size="small" @click.prevent="clickBtn"/>
        <h2 class="content__btn-title">(secondary)</h2>
        <BaseButtonVue class="content__btn" label="Отправить&nbsp;письмо" color="secondary" size="small" @click.prevent="clickBtn"/>
        <h2 class="content__btn-title">(warning)</h2>
        <BaseButtonVue class="content__btn" label="Отправить&nbsp;письмо" color="warning" size="small" @click.prevent="clickBtn"/>
        <h2 class="content__btn-title">(disabled)</h2>
        <BaseButtonVue class="content__btn" label="Отправить&nbsp;письмо" color="disabled" size="small" @click.prevent="clickBtn"/>
        <h2 class="content__btn-title">(info)</h2>
        <BaseButtonVue class="content__btn" label="Отправить&nbsp;письмо" color="info" @click.prevent="clickBtn"/>
        <h2 class="content__btn-title">(danger)</h2>
        <BaseButtonVue class="content__btn" label="Отправить&nbsp;письмо" color="danger" @click.prevent="clickBtn"/>
        <h2 class="content__btn-title">(action)</h2>
        <BaseButtonVue class="content__btn" label="Отправить&nbsp;письмо" color="action" @click.prevent="clickBtn"/>
      </div>
      <div class="content__wrapper">
        <h2 class="content__title">(button multi-sized)</h2>
        <div class="content__btn-group">
          <BaseButtonVue class="content__btn" icon="icon-arrow" type="icon" color="primary" size="small" @click.prevent="clickBtn"/>
          <BaseButtonVue class="content__btn" icon="icon-arrow" type="icon" color="primary" @click.prevent="clickBtn"/>
        </div>
        <div class="content__btn-group">
          <BaseButtonVue class="content__btn" icon="icon-exit" type="icon" color="danger" size="small" @click.prevent="clickBtn"/>
          <BaseButtonVue class="content__btn" icon="icon-exit" type="icon" color="danger" @click.prevent="clickBtn"/>
        </div>
        <div class="content__btn-group">
          <BaseButtonVue class="content__btn" icon="icon-quest" type="icon" color="info" size="small" @click.prevent="clickBtn"/>
          <BaseButtonVue class="content__btn" icon="icon-quest" type="icon" color="info" @click.prevent="clickBtn"/>
        </div>
        <div class="content__btn-group">
          <BaseButtonVue class="content__btn" icon="icon-arrow1" type="icon" color="primary" size="small" @click.prevent="clickBtn"/>
          <BaseButtonVue class="content__btn" icon="icon-arrow1" type="icon" color="primary" @click.prevent="clickBtn"/>
        </div>
        <div class="content__btn-group">
          <BaseButtonVue class="content__btn" icon="icon-google" type="icon" color="danger" size="small" @click.prevent="clickBtn"/>
          <BaseButtonVue class="content__btn" icon="icon-google" type="icon" color="danger" @click.prevent="clickBtn"/>
        </div>
        <div class="content__btn-group">
          <BaseButtonVue class="content__btn" icon="icon-vk" type="icon" color="info" size="small" @click.prevent="clickBtn"/>
          <BaseButtonVue class="content__btn" icon="icon-vk" type="icon" color="info" @click.prevent="clickBtn"/>
        </div>
        <div class="content__btn-group">
          <BaseButtonVue class="content__btn" icon="icon-class" type="icon" color="action" size="small" @click.prevent="clickBtn"/>
          <BaseButtonVue class="content__btn" icon="icon-class" type="icon" color="action" @click.prevent="clickBtn"/>
        </div>
        <div class="content__btn-group">
          <BaseButtonVue class="content__btn" icon="icon-pen" type="icon" color="primary" size="small" @click.prevent="clickBtn"/>
          <BaseButtonVue class="content__btn" icon="icon-pen" type="icon" color="primary" @click.prevent="clickBtn"/>
        </div>
      </div>
      <div class="content__wrapper">
        <h2 class="content__title">(button link)</h2>
        <BaseButtonVue href="#" class="content__btn" label="Напомнить PIN-код" type="link" @click.prevent="clickBtn"/>
      </div>
      <div class="content__wrapper">
        <h2 class="content__title">(button timer)</h2>
        <BaseButtonVue 
        class="content__btn" 
        label="повторное письмо" 
        type="timer" 
        :color="this.color"
        :timer="this.currentTime"
        @click.prevent="restartTimer"/>
      </div>
    </div>
  </div>
</template>

<style lang="scss">
@import "@/styles/global.scss";
@import "@/styles/icons.css";

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
  }
  &__btn {
    margin-bottom: 24px;
  }
}
</style>
