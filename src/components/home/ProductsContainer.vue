<template>
  <div>
    <v-container class="px-md-0">
        <div class="section-header w-100 py-5 d-flex justify-space-between align-center">
            <h2 class="text-md-h6 text-body-1 font-weight-medium text-capitalize upper">{{ title }}</h2>
            <v-hover v-slot="{isHovering, props}">
                <v-btn v-if="to" :link="true" :to="to" v-bind="props" class="no-hover text-capitalize pr-0" variant="text" :ripple="false" color="primary-purple">See All<v-icon class="t-duration-1" :class="isHovering ? 'ml-4 mr-n2' : 'ml-2'">mdi-arrow-right</v-icon></v-btn>
            </v-hover>
        </div>
        <div class="products">
            <v-row>
                <v-col cols="12" sm="6" md="3" v-for="product in products" :key="product.id">
                    <ProductCard :product="product" />
                </v-col>
            </v-row>
        </div>

    </v-container>
  </div>
</template>

<script>
import ProductCard from './ProductCard.vue';

export default {
    props: ['title', 'products', 'to'],
    data() {
        return {
            
        };
    },
    components: { ProductCard }
}
</script>

<style scoped>

.t-duration-1 {
    transition-duration: .3s;
}

.upper {
    text-transform: capitalize !important;
}

</style>