<template>
    <ul>
        <li v-for="(item, index) in va" :key="index">{{ item.title }}</li>
    </ul>
</template>
<script>
import axios from 'axios'
import va from './m21.js'
export default {
    data() {
        return {
            va
        }
    },
    methods: {
    },
}
</script>