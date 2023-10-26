<template>
    <div class="block__card" >
        <product-card v-for="card in cardDataList" :key="card.id" :card-data="card"/>
    </div>
</template>


<script>
import ProductCard from "./ProductCard.vue";
    export default {
        name:'ProductCardList',
        components: {
            ProductCard,
        },
        props: {
            cardDataList: {
                type: Array,
                default: ()=>[]
            },
        },
    }
</script>

<style lang="css" scoped>
.block__card{
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 30px;
}
</style>