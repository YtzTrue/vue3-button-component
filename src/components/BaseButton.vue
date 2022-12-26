<script>
export default {
    props: {
        type: {
            type: String,
            default: 'button'
        },
        size: {
            type: String,
            default: 'normal'
        },
        label: {
            type: String,
            default: ''
        },
        color: {
            type: String,
            default: ''
        },
        icon: {
            type: String,
            default: ''
        },
        href: {
            type: String,
            default: ''
        }
    },
    data() {
        return {}
    },
    methods: {
        click() {
            this.$emit('click')
        }
    }
}
</script>

<template>
    <div 
    class="button"
    :class="[`button_${type}`, `button_${type}_${size}`, `button_${color}`, ]">
        <span :class="`${icon}`" v-if="type === 'icon'"></span>
        <span v-if="type === 'button'">
            {{ label }}
        </span>
        <a v-if="type === 'link'" :href="href">{{ label }}</a>
    </div>
</template>

<style scoped lang="scss">

    .button {
        display: flex;
        align-items: center;
        justify-content: center;
        height: 60px;
        border-radius: 20px;
        border: none;
        outline: none;
        font-family: Phoshate, Helvetica, Arial, sans-serif;
        font-weight: 400;
        font-size: 18px;
        line-height: 24px;
        color: #fff;
        cursor: pointer;
        // types
        &_button {
            padding: 0px 60px;
            @media(max-width: 640px) {
                height: 52px;
                padding: 0px 46px;
            }
            &_small {
                height: 52px;
                padding: 0px 46px;
            }
        }
        &_icon {
            padding: 0;
            height: 60px;
            width: 60px;
            font-size: 28px;
            @media(max-width: 640px) {
                height: 52px;
                width: 52px;
                font-size: 22px;
            }
            &_small {
                height: 52px;
                width: 52px;
                font-size: 22px;
            }
        }
        &_link {
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
            :hover {
                color: #767679;
                border-bottom: 1px solid #767679;
            }
            :active {
                color: #C4296C;
                border-bottom: 1px solid #C4296C;
            }
        }
        // colors
        &_primary {
            background-color: var(--primary);
        }
        &_secondary {
            background-color: var(--secondary);
        }
        &_warning {
            background-color: var(--warning);
        }
        &_disabled {
            background-color: var(--disabled);
            color: #767679;
            pointer-events: none;
        }
        &_info {
            background-color: var(--info);
        }
        &_danger {
            background-color: var(--danger);
        }
        &_action {
            background-color: var(--action);
        }

        span {
            vertical-align: middle;
        }
    }
</style>