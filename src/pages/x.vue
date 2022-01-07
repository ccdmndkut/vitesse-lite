<template>
    <input
        :disabled="loading"
        ref="inp"
        id="input"
        v-model="q"
        type="text"
        autocomplete="false"
        p="x-4 y-2"
        w="250px"
        text="center"
        bg="transparent"
        border="~ rounded gray-200 dark:gray-700"
        outline="none active:none"
        @keydown.enter="getx"
    />
    <div>
        <button id="getbtn" :disabled="!q || loading" class="m-3 text-sm btn" @click="getx(q)">Go</button>
    </div>
    <div>{{ xdata }}</div>
</template>


<script>
import axios from 'axios'
export default {
    data() {
        return {
            q: '',
            loading: false,
            xdata: null
        }
    },
    watch: {
        loading(v) {
            if (v) document.title = 'Loading'
            else document.title = this.xdata.length
        }
    },
    methods: {
        async getx() {
            this.xdata = null
            this.loading = true
            let { data } = await axios.get('https://goo.iamlyrics.com/api/xnxxs/' + this.q)
            this.xdata = data
            this.loading = false
        }
    },
    mounted() {
    },
}
</script>
<style>
</style>