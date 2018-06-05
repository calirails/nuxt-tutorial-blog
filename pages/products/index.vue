<template>
    <div>
        <input type='text' v-model='productId'/>
        <button v-on:click='loadProduct'>Load Product</button>
        <ul>
            <li v-for='framework in frameworks' v-bind:key='framework.id'>
                <!-- Note: oddly that to=<val> alone does not work but :to=<val> does work -->
                <!-- <nuxt-link v-bind:to="'/products/' + framework.id">{{framework.desc}}</nuxt-link> -->
                <!-- Note: oddly binding 'pathForProductDetails' does not work as a computed property but works as method, 
                           And yes, we can also use ':to=<val>' instead of v-bind:to but the latter is reliable' -->
                <nuxt-link v-bind:to='pathForProductDetails(framework)'>{{framework.desc}}</nuxt-link>
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
    methods: {
        loadProduct() {
            this.$router.push(`/products/${this.productId}`);
        },
        pathForProductDetails(framework) {
            return `/products/${framework.desc}`;
        }
    }
}
</script>


