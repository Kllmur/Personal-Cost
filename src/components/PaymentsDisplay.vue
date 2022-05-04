<template>
    <div class="paymentDisplay"> 
    {{ items }}
    </div>
</template>

<script>
export default {
    name: "PaymentsDisplay",
    props: {
        items: {
            type: Array,
            default: ()=>[],
        }
    },
}
</script>

<style lang="scss" module>
</style>
