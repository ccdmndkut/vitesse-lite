<template>
    <div>
        <router-link v-if="rt" :to="'/' + rt">
            <button class="btn">{{ rt }}</button>
        </router-link>
    </div>

    <input
        v-model="rt"
        type="text"
        autocomplete="false"
        p="x-4 y-2"
        w="250px"
        text="center"
        bg="transparent"
        border="~ rounded gray-200 dark:gray-700"
        outline="none active:none"
    />
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
            rt: '',
            todo: ['Green', 'Arstingstall', 'Hall']
        }
    },

}
</script>