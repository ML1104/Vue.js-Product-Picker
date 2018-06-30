<template>
    <div id="summaryBox">
        <div class="flexbox">
            <div>
                <div class="title">Order Summary</div>
                <br>
                <br>
                <div class="totalPrice">${{ price + " +"}} ${{durationPrice + " +"}} ${{supportChoicePrice}}</div>
                <div>(Total Excluding Tax)</div>
                <div><span class="price">${{ price }}</span> Per User Per Year</div>
            </div>
            <div>
                <div class="title">Details</div>
                <br>
                <br>
                <div class="details">PRODUCT: <span>{{ edition }}</span></div>
                <div class="details">QUANTITY: <span>{{ quantity }}</span></div>
                <div class="details">DURATION: <span>{{ duration }}</span></div>
                <div class="details">SUPPORT: <span>{{ support }}</span></div>
            </div>
            <div id="submit">
                <div>ORDER</div>
            </div>
        </div>
    </div>
</template>


<script>
export default {
    name: "Summary",

    props: {
        edition: { required: true },
        price: { required: true },
        quantity: { required: true },
        duration: { required: true },
        durationPrice: { required: true },
        support: { required: true },
        supportChoicePrice: { required: true },
    },

    data: function() {
        return {
            users: "",
            yearPrice: "",
            supportPrice: "",
            discounted: "",
        } 
    },

    mounted: function() {
        this.checkPrice();
    },

    methods: {
        checkPrice: function() {
            this.$emit('priceCheck');
        },
    }
}
</script>

<style scoped>
    #summaryBox {
        background-color: #2F3241;
        color: white;
        height: 400px;
        display: flex;
        align-items: center;
        justify-content: center;
    }

    .flexbox {
        display: flex;
        justify-content: space-around;
        align-items: center;
        height: 200px;
        width: 100%;
        line-height: 40px;
    }

    #submit {
        display: flex;
        justify-content: center;
        align-items: center;
    }

    #submit:hover {
        cursor: pointer;
    }

    #submit div {
        background-color: white;
        color: #2F3241;
        width: 200px;
        border-radius: 5px;
    }

    .title {
        font-size: 20px;
    }

    span {
        color: #9FEAF9;
    }

    .totalPrice {
        font-size: 30px;
        color: #9FEAF9;
    }
</style>


