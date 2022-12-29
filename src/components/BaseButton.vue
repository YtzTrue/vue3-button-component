<script setup>
const props = defineProps({
  type: {
    type: String,
    default: 'button'
  },
  size: {
    type: String,
    default: 'normal'
  },
  color: {
    type: String,
    default: 'primary'
  },
  disabled: {
    type: Boolean,
    required: false
  },
  icon: {
    type: String,
    default: ''
  },
  href: {
    type: String,
    default: ''
  },
  timer: {
    type: String,
    default: '00:00'
  }
})
const emit = defineEmits(['click'])

const click = () => {
  emit('click')
}
</script>

<template>
  <button v-if="type === 'button' || type === 'timer' || type === 'icon'" class="button"
    :class="[`button_${type}`, `button_${type}_${size}`, `button_${color}`,]" :disabled="disabled" @click="click">
    <span :class="`${icon}`" v-if="type === 'icon'">
      <slot></slot>
    </span>
    <span v-if="type === 'button' || type === 'timer'">
      <slot></slot>
    </span>
    <div v-if="type === 'timer'" class="timer-wrapper">
      <span class="timer">{{ timer }}</span>
    </div>
  </button>
  <a class="link" v-if="type === 'link'" :href="href">
    <slot></slot>
  </a>
</template>

<style scoped lang="scss">
.button {
  position: relative;
  display: flex;
  align-items: center;
  justify-content: center;
  height: 60px;
  border: none;
  outline: none;
  font-family: Phoshate, Helvetica, Arial, sans-serif;
  font-weight: 400;
  font-size: 18px;
  line-height: 24px;
  color: #fff;
  cursor: pointer;
  user-select: none;

  // types
  &_button,
  &_timer {
    margin-left: 46px;
    margin-right: 46px;
    height: 52px;
    padding: 0px 2px;

    ::before {
      content: '';
      position: absolute;
      transform: rotate(180deg);
      top: 0;
      left: -44px;
      width: 46px;
      height: 52px;
      overflow: hidden;
      clip-path: path("M0 51.9694V0.0467095C7.62125 -0.0384196 14.9744 -0.00900615 19.91 0.149932C32.3106 0.549263 39.1023 0.919741 42.86 9.3057C45.4933 15.1822 45.9983 23.7337 46 29.0811C46 29.0997 46 29.1183 46 29.1368C45.9993 31.3922 45.9093 33.0692 45.8535 33.7211C45.8423 33.8518 45.8315 34.0019 45.8194 34.1697C45.6278 36.8224 45.1159 43.9105 37.8709 48.9807C34.1516 51.5835 17.2812 52.1493 0 53Z");
    }

    ::after {
      content: '';
      position: absolute;
      top: 0;
      right: -44px;
      width: 46px;
      height: 52px;
      overflow: hidden;
      clip-path: path("M0 51.9694V0.0467095C7.62125 -0.0384196 14.9744 -0.00900615 19.91 0.149932C32.3106 0.549263 39.1023 0.919741 42.86 9.3057C45.4933 15.1822 45.9983 23.7337 46 29.0811C46 29.0997 46 29.1183 46 29.1368C45.9993 31.3922 45.9093 33.0692 45.8535 33.7211C45.8423 33.8518 45.8315 34.0019 45.8194 34.1697C45.6278 36.8224 45.1159 43.9105 37.8709 48.9807C34.1516 51.5835 17.2812 52.1493 0 53Z");
    }
  }

  &_icon {
    padding: 0;
    height: 60px;
    width: 60px;
    font-size: 28px;
    clip-path: var(--icon-path);

    @media(max-width: 640px) {
      height: 52px;
      width: 52px;
      font-size: 22px;
      clip-path: var(--icon-path-small);
    }

    &_small {
      height: 52px;
      width: 52px;
      font-size: 22px;
      clip-path: var(--icon-path-small);
    }
  }

  // colors
  &_primary {
    background-color: var(--primary);

    ::before,
    ::after {
      background-color: var(--primary);
    }
  }

  &_secondary {
    background-color: var(--secondary);

    ::before,
    ::after {
      background-color: var(--secondary);
    }
  }

  &_warning {
    background-color: var(--warning);

    ::before,
    ::after {
      background-color: var(--warning);
    }
  }

  &:disabled {
    background-color: var(--disabled);
    color: #767679;

    ::before,
    ::after {
      background-color: var(--disabled);
    }
  }

  &_info {
    background-color: var(--info);

    ::before,
    ::after {
      background-color: var(--info);
    }
  }

  &_danger {
    background-color: var(--danger);

    ::before,
    ::after {
      background-color: var(--danger);
    }
  }

  &_action {
    background-color: var(--action);

    ::before,
    ::after {
      background-color: var(--action);
    }
  }

  span {
    vertical-align: middle;
  }
}

.button::after {
  content: '';
  position: absolute;
  top: 0;
  right: -44px;
  width: 46px;
  height: 52px;
  overflow: hidden;
  clip-path: path("M0 51.9694V0.0467095C7.62125 -0.0384196 14.9744 -0.00900615 19.91 0.149932C32.3106 0.549263 39.1023 0.919741 42.86 9.3057C45.4933 15.1822 45.9983 23.7337 46 29.0811C46 29.0997 46 29.1183 46 29.1368C45.9993 31.3922 45.9093 33.0692 45.8535 33.7211C45.8423 33.8518 45.8315 34.0019 45.8194 34.1697C45.6278 36.8224 45.1159 43.9105 37.8709 48.9807C34.1516 51.5835 17.2812 52.1493 0 53Z");
}

.link {
  height: unset;
  margin: 0;
  padding: 0;
  background-color: unset;
  font-family: Helvetica, Arial, sans-serif;
  font-weight: 700;
  font-size: 16px;
  line-height: 18px;
  border-radius: unset;
  color: #fff;

  &:hover {
    color: #767679;
    border-bottom: 1px solid #767679;
    margin-bottom: -1px;
  }

  &:active {
    color: #C4296C;
    border-bottom: 1px solid #C4296C;
    margin-bottom: -1px;
  }
}

.timer-wrapper {
  display: flex;
  align-items: center;
  justify-content: center;
  margin-left: 10px;
  width: 54px;
  height: 26px;
  background-color: var(--danger);
  clip-path: var(--timer-path);
}

.timer {
  color: #fff;
}
</style>
