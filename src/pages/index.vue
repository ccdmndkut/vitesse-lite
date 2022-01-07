<template>
    <input
        id="input"
        v-model="q"
        placeholder="Search"
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
        <button :disabled="!q" class="m-3 text-sm btn" @click="getx">Go</button>
    </div>
</template>


<script>
import axios from 'axios'

export default {
    data() {
        return {
            q: ''
        }
    },
    methods: {
        async getx() {
            let { data } = await axios.get('https://goo.iamlyrics.com/api/xnxxs/blonde')
            console.log(data);
        }
    },
    mounted() {
        console.log('mounted');
    },
}
</script>