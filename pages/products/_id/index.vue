<template>
    <div>
        Details for Product ID: {{$route.params.id}}
    </div>
</template>


<script>
export default {
    name: 'ProductDetail',
    validate(data) {
        // Only allow numeric identifiers
        if (/^\d+$/.test(data.params.id)) {
            console.log(data);
            return true;
        } else {
            console.log('validation failed');
            return false;
        }
    }
}
</script>
