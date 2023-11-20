<template>
    <div class="restaurant--row">
        <h2 class="title">
            Nos Restaurants
            {{ toto }}
        </h2>
        <div class="wrapper--card">
            <RouterLink v-for="(restaurant, index) in three_restaurant" :key="index"
                :to="{ name: 'Restaurant', params: { name: restaurant.name } }">

                <RestaurantCard :info_restaurant="card" />
            </RouterLink>


        </div>
    </div>
</template>

<script>
import RestaurantCard from './RestaurantCard.vue';
export default {
    name: "RestaurantRow",
    components: {
        RestaurantCard,
    },
    // le tableau de carte va s'adapter au tableau 
    props: {
        three_restaurant: Array
    }

}
</script>

<style lang="scss">
.restaurant--row {
    .title {
        font-style: 2rem;
    }

    .wrapper--card {
        display: flex;
        align-items: center;
        justify-content: space-between;
    }
}
</style>