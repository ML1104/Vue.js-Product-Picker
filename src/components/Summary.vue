<template>
    <div id="summaryBox">
        <div class="flexbox">
            <div v-on:selectStandard="standardVersion">
                <div class="title">Order Summary</div>
                <br>
                <br>
                <div class="totalPrice">{{ totalPrice }}</div>
                <div>(Total Excluding Tax)</div>
                <div><span class="price">$0</span> Per User Per Year</div>
                <div>Add Multi-User Discount</div>
                <div>Add Multi-Year Discount</div>
            </div>
            <div>
                <div class="title">Details</div>
                <br>
                <br>
                <div>PRODUCT: <span>{{ edition }}</span></div>
                <div>QUANTITY: <span></span></div>
                <div>DURATION: <span></span></div>
                <div>SUPPORT: <span></span></div>
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

    data: function() {
        return {
            totalPrice: "$",
            users: "",
            yearPrice: "",
            supportPrice: "",
            edition: "",
        } 
    },

    methods: {
        standardVersion: function() {
            this.edition = "Standard"
            this.totalPrice += 150;
        }
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

    .totalPrice {
        font-size: 30px;
        color: #9FEAF9;
    }
</style>


