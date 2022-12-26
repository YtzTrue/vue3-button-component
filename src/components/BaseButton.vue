<script>
export default {
    props: {
        label: {
            type: String,
            default: 'Button'
        },
        color: {
            type: String,
            default: 'primary'
        },
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
    :class="[`button_${color}`]">
        <span>
            {{ label }}
        </span>
    </div>
</template>

<style scoped lang="scss">
    .button {
        padding: 12px 46px;
        height: 52px;
        border-radius: 20px;
        border: none;
        outline: none;
        font-family: Phoshate, Helvetica, Arial, sans-serif;
        font-weight: 400;
        font-size: 18px;
        line-height: 24px;
        color: #fff;
        cursor: pointer;

        span {
            vertical-align: middle;
        }
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
    }
</style>