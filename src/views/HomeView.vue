<template>
    <div class="home">

        <h2>{{appTitle}}</h2>

        <h3>{{counterData.title}}:</h3>

        <div>
            <button @click="decreaseCounter(2)" class="btn">--</button>
            <button @click="decreaseCounter(1)" class="btn">-</button>
            <span class="counter">{{counterData.count}}</span>
            <button @click="increaseCounter(1, $event)" class="btn">+</button>
            <button @click="increaseCounter(2, $event)" class="btn">++</button>
        </div>

        <p>This counter is {{oddOrEven}}</p>

        <div class="edit">
            <h4>Edit counter title:</h4>
            <input v-model="counterData.title" type="text">
        </div>

    </div>
</template>


<script setup>
import {
    computed,
    onActivated,
    onBeforeMount,
    onBeforeUnmount,
    onDeactivated,
    onMounted,
    onUnmounted,
    reactive,
    watch
} from "vue";

const appTitle = 'My Ok Counter App'

const counterData = reactive({
    count: 0,
    title: 'My Counter'
})

watch(() => counterData.count, (newCount, oldCount) => {
    if (newCount === 20) alert('Way to go! You made it to 20!!')
    if (oldCount === 20) alert('Stop! You just passed 20!!')
})

const oddOrEven = computed(() => {
    if (counterData.count % 2 === 0) return 'even'
    else return 'odd'
})

function increaseCounter(amount, e) {
    console.log(e)
    counterData.count += amount
}
const decreaseCounter = amount => {counterData.count -= amount}

onBeforeMount(() => {
    console.log('onBeforeMount')
})
onMounted(() => {
    console.log('onMount')
})
onBeforeUnmount(() => {
    console.log('onBeforeUnmount')
})
onUnmounted(() => {
    console.log('onUnmounted')
})
onActivated(() => {
    console.log('onActivated')
})
onDeactivated(() => {
    console.log('onDeactivated')
})

</script>


<!--
<script>
export default {
    data() {
        return {
            count: 0
        }
    },
    computed: {
        myComputedProperty() {
            return 'my result'
        }
    },
    watch: {
        count(newCount, oldCount) {
            if (newCount == 20) alert('asdfasd')
        }
    },
    mounted() {
        console.log('mounted')
    },
    unmounted() {
        console.log('unmounted')
    }
}
</script>
-->


<style>
.home {
    text-align: center;
    padding: 20px;
}
.btn, .counter {
    font-size: 40px;
    margin: 10px;
}
.edit {
    margin-top: 60px;
}
</style>
