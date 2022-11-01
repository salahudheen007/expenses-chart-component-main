<template>
    <div class="col-1">
        <p :class="['amount']">{{ '$' + ht }}</p>
        <div class="bar rounded text-center" :style="[{ height: (ht / mx) * 150 + 'px' }]"
            :class="[ht == mx ? 'cyan_bg' : 'orange_bg']" 
            :data-tooltip="'$'+ht">
        </div>
        <p class="day mt-2 mb-2">{{ day }}</p>
    </div>
</template>

<script setup>

import { Tooltip } from "bootstrap";
import {  onMounted } from 'vue'
const props = defineProps({
    ht: Number,
    mx: Number,
    day: String

})




</script>

<style  scoped>
.col-1 {
    width: 14%;
}

.bar {
    width: 100%;
    position: relative;
}

.orange_bg {
    background-color: var(--Soft-red);
}

.cyan_bg {
    background-color: var(--Cyan);
}

.day {
    font-size: 14px;
    color: var(--Medium-brown);
}

.amount {
    display: none;
    position: relative;
}
.bar:hover::before{
    content: attr(data-tooltip);
    position: absolute ;
    top: -2.2rem;
    left: 50%;
    height: 30px;
    width: 140%;
    background-color: var(  --Dark-brown);
    color: var(--Cream);
    border-radius: 5px;
    padding: 3px;
    transform: translateX(-50%);
}
@media only screen and (max-width: 400px) {
    .bar:hover::before{
        width: 160%;
    }
}
</style>