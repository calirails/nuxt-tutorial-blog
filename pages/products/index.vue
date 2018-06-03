<template>
    <div>
        <input type='text' v-model='productId'/>
        <button v-on:click='loadProduct'>Load Product</button>
    </div>
</template>

<script>
export default {
    name: 'Products',
    data() {
        return {
            productId: null
        }
    },
    methods: {
        loadProduct() {
            this.$router.push(`/products/${this.productId}`);
        }
    }
}
</script>


