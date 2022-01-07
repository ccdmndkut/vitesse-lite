<template>
    <router-link to="/x">x</router-link>
    <div>
        <ul text-4xl>
            <li v-for="(item, index) in todo" :key="index">
                <h1>{{ item }}</h1>
            </li>
        </ul>
    </div>
</template>


<script>
export default {
    data() {
        return {
            todo: ['Henson', 'Arstingstall', 'Hall']
        }
    },
    methods: {

    },
    mounted() {
    },
}
</script>