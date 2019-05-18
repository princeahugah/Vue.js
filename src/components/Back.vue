<template>
    <li class="tool-icon" ref="back" data-position="bottom" data-tooltip="Back" 
        @click="navigateTo">
        <i class="material-icons">chevron_left</i>
    </li>
</template>

<script>
export default {
    name: 'Back',

    props: {
        options: {
            type: Object,
            default() {
                return { location: '/' };
            }
        }
    },
    
    mounted() {
        this.setupTooltip();
    },

    methods: {
        setupTooltip() {
            const { Tooltip } = window.M;
            Tooltip.init(this.$refs.back);
        },

        navigateTo() {
            this.$router.push(this.options.location);
        }
    }
};
</script>