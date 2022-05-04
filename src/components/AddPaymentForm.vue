<template>

    <div>

    <button @click="isHidden=!isHidden">ADD NEW COST</button>

    <div class="paymentForm" v-show="isHidden" > 

        <input placeholder="Date" v-model="date" />
        <input placeholder="Category" v-model="category" />
        <input placeholder="Value" v-model="value" />
        <button @click="onSaveClick">Save!</button>

    </div>

    </div>

</template>

<script>
 export default {
    name:"AddPaymentForm",
    data() {
        return {
            date: '',
            category: '',
            value: '',
            isHidden: false,
        }
    },

    computed: {

        // getCurrentDate() {
        //     const today = new Date();
        //     const day = today.getDate();
        //     const month = today.getMonth() + 1;
        //     const year = today.getFullYear();
        //     return `${day}.${month}.${year}`;
        // },

        currentDate() {
            let data = new Date();
            const today = new Intl.DateTimeFormat("ru").format(data);
            return `${today}`;
        }
    },

    methods: {
        onSaveClick() {
            const data = {
                date: this.date || this.currentDate,
                category: this.category,
                value: this.value,
            }
            this.$emit('addNewPayment', data)
        }
    }
}
</script>

<style lang="scss">

</style>
