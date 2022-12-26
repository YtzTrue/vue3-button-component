<script>
import BaseButtonVue from './components/BaseButton.vue'

export default {
  name: 'app',
  components: { BaseButtonVue },
  data() {
    return {}
  },
  methods: {
    clickBtn() {
      console.log('click')
    }
  }
}
</script>

<template>
  <div class="container">
    <h1>This is Vue3-button-component</h1>
    <div class="content">
      <div class="content__wrapper">
        <h2 class="content__title">(button-classic)</h2>
        <h2 class="content__btn-title">(primary)</h2>
        <BaseButtonVue class="content__btn" label="Отправить письмо" color="primary" @click.prevent="clickBtn"/>
        <h2 class="content__btn-title">(secondary)</h2>
        <BaseButtonVue class="content__btn" label="Отправить письмо" color="secondary" @click.prevent="clickBtn"/>
        <h2 class="content__btn-title">(warning)</h2>
        <BaseButtonVue class="content__btn" label="Отправить письмо" color="warning" @click.prevent="clickBtn"/>
        <h2 class="content__btn-title">(disabled)</h2>
        <BaseButtonVue class="content__btn" label="Отправить письмо" color="disabled" @click.prevent="clickBtn"/>
        <h2 class="content__btn-title">(info)</h2>
        <BaseButtonVue class="content__btn" label="Отправить письмо" color="info" @click.prevent="clickBtn"/>
        <h2 class="content__btn-title">(danger)</h2>
        <BaseButtonVue class="content__btn" label="Отправить письмо" color="danger" @click.prevent="clickBtn"/>
        <h2 class="content__btn-title">(action)</h2>
        <BaseButtonVue class="content__btn" label="Отправить письмо" color="action" @click.prevent="clickBtn"/>
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
  &__wrapper {
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    justify-content: space-between;
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
  &__btn {
    margin-bottom: 24px;
  }
}
</style>
