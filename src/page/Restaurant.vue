<template>
    <router-link to="/">
        <div id="return"> retour à l page d'acceuil</div>
    </router-link>
    <div>
        <img :src="restaurant.image" alt="">
    </div>
    <p>{{ restaurant.name }}</p>
    <p> note du restaurant {{ restaurant.restaurant }}</p>
    <p> Temps de livraison{{ restaurant.drive_time }}</p>
</template>

<script>
import BDD from '../BDD'

import { useRoute } from 'vue-router'


export default {
    name: 'Restaurant',
    setup() {
        const route = useRoute()
        const restaurant = BDD.find((restaurant) => restaurant.name === route.params.name)

        return { restaurant }
    }
}


</script>

<style lang="scss" scoped>
#return {
    margin-bottom: 25px 45px;

    font-weight: 400;
    cursor: pointer;
    text-decoration: none;
    pointer-events: none;
    underline: none;

    &:hover {
        font-size: 30px
    }

}
</style>