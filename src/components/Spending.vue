<template>
    <div class="card">
        <div class="card-body">
            <h3 class="card-title text-start mt-3 mb-5">Spending - Last 7 days</h3>
            <div class="row g-2 justify-content-around align-items-end">
                <bar  v-for="item in data" :ht=item.amount :mx=maxSpend :day="item.day"/>
            </div>
            <hr class="mb-4">
            <div class="row footer py-1">
                <div class="col">
                    <p class="mb-1">Total this month</p>
                    <h2 class="mt-1">$478.33</h2>
                </div>
                <div class="col text-end pb-0 pt-4">
                   <h6 class="mb-0">+2.4%</h6>
                   <p class="mb-0">from last month</p>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup>
import bar from './bar.vue'
import data from '../assets/data.json'
import { computed } from 'vue';

const maxSpend=computed(()=>{
    const amounts=data.map(x=>x.amount)
    return amounts[amounts.indexOf(Math.max(...amounts))]
})
</script>

<style  scoped>
@media only screen and (max-width: 400px) {
    .card {
        width: 21rem;
    }
}

@media only screen and (min-width: 401px) {
    .card {
        width: 25rem;
        padding:.7rem
    }
}

.card-title {
    color: var(--Dark-brown);
    font-weight: 700;
}.card{
    border-radius: 15px;
    border: none;
}
h2{
    color: var(--Dark-brown);
    font-weight: 700;

}
p{
    font-size: 1.1rem;
    color: var(--Medium-brown);
}
h6{
    font-weight: 700;
}
</style>