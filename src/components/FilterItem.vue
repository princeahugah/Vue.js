<template>
    <li @click="filterBy(filterItemName)">
        <span>
            <i v-show="activeItem === filterItemName" class="material-icons">check</i>
            <slot></slot>
        </span>
    </li>
</template>

<script>
export default {
    name: 'FilterItem',

    props: {
        activeItem: {
            type: String,
            required: true
        },

        filterItemName: {
            type: String,
            required: true
        },

        filterBy: {
            type: Function,
            required: true 
        }
    }
};
</script>