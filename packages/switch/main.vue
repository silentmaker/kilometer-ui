<template>
    <div :class="['switch', enabled ? '' : 'off']" @click="toggle">
        <div class="handle"></div>
    </div>
</template>

<script>
export default {
    name: 'km-switch',
    props: {
        value: {
            type: Boolean,
            default: false,
        },
    },
    data() {
        return {
            enabled: false,
        };
    },
    mounted() {
        this.enabled = this.value;
    },
    watch: {
        value(val) {
            this.enabled = val;
        },
    },
    methods: {
        toggle() {
            this.enabled = !this.enabled;
            this.$emit('input', this.enabled);
        }
    },
}
</script>

<style lang="postcss" scoped>
.switch {
    position: relative;
    display: inline-block;
    width: 32px;
    height: 18px;
    vertical-align: middle;
    background-color: #04be02;
    border: solid 1px transparent;
    border-radius: 14px;
    transition: background-color 0.5s;
    cursor: pointer;

    .handle {
        position: absolute;
        top: 1px;
        right: 1px;
        width: 14px;
        height: 14px;
        border-radius: 50%;
        background-color: #fff;
        transition: background-color,transform 0.5s;
    }
    &.off {
        background-color: #fff;
        border: solid 1px #dcdcdc;

        .handle {
            transform: translateX(-13px);
            background-color: #04be02;
        }
    }
}
</style>
