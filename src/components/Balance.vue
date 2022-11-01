<template>
    <div class="card mb-4" >
        <div class="row g-0 justify-content-between py-1 px-1">
            <div class="col-8">
                <div class="card-body text-start py-3">
                    <h6 class="card-title">My balance</h6>
                    <p class="card-text">$921.48</p>
                </div>
            </div>
            <div class="col-4 py-4">
                <img :src="logo" class="img-fluid rounded-start" alt="Logo">
            </div>
        </div>
    </div>
</template>

<script setup>
import logo from '../assets/images/logo.svg'
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
  }
}
.card{
    background-color: var(--Soft-red);
    border-radius: 15px;
    font-size: 18px;
    color: var( --Very-pale-orange);
}
.card-text{
    font-weight: 700;
    font-size: 1.6rem;
}
.card-title,.card-tex{
  color:var(--Very-pale-orange);
}
</style>