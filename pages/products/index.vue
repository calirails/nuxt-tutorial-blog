<template>
    <div>
        <input type='text' v-model='productId'/>
        <button v-on:click='loadProduct'>Load Product</button>
        <ul>
            <li v-for='framework in frameworks' v-bind:key='framework.id'>
                <nuxt-link v-bind:to="'/products/' + framework.id">{{framework.desc}}</nuxt-link>
            </li>
        </ul>
    </div>
</template>

<script>
export default {
    name: 'Products',
    data() {
        return {
            productId: null,
            frameworks: [
                {id: 1, desc: 'VueJS'},
                {id: 2, desc: 'Nuxt'}
            ]
        }
    },
    computed: {
        pathForProductDetails(framework) {
            return `/products/${framework.desc}`;
        }
    },
    methods: {
        loadProduct() {
            this.$router.push(`/products/${this.productId}`);
        }
    }
}
</script>


