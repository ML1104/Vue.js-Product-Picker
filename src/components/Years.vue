<template>
    <div class="pageWrapper">

        <h1 class="sectionName">How Many Years?</h1>

        <div class="alignCenter">
            <div class="optionBox" v-bind:class="{ 'selected' : oneSelected }">
                <div>
                    <div class="title">1 Year</div>
                </div>
                <div>
                    <div class="description">
                     Standard
                    </div>
                </div>
                <div>
                    <div class="price">$Free</div>
                    <div class="description">as default</div>
                    <div class="selectedButton" v-on:click="selectedOne">Select</div>
                </div>
            </div>

            <div class="optionBox" v-bind:class="{ 'selected' : twoSelected }">
                <div>
                    <div class="title">2 Years</div>
                </div>
                <div>
                    <div class="description">
                     Get 50% off your second year!
                    </div>
                </div>
                <div>
                    <div class="price">+ $74</div>
                    <div class="description">per license</div>
                    <div class="selectedButton" v-on:click="selectedTwo">Select</div>
                </div>
            </div>

            <div class="optionBox" v-bind:class="{ 'selected' : threeSelected }">
                <div>
                    <div class="title">3 Years</div>
                </div>
                <div>
                    <div class="description">
                     Get 50% off your third year too!
                    </div>
                </div>
                <div>
                    <div class="price">+ $149</div>
                    <div class="description">per license</div>
                    <div class="selectedButton" v-on:click="selectedThree">Select</div>
                </div>
            </div>
        </div>

    </div>

        
</template>


<script>
export default {
    name: "Years",

    data: function() {
        return {
            oneSelected: false,
            twoSelected: false,
            threeSelected: false,
        }
    },


    methods: {
        selectedOne: function() {
            if (this.oneSelected === false) {
                this.oneSelected = true;
                this.twoSelected = false;
                this.threeSelected = false;
            } else {
                this.oneSelected = false;
            }
        },

        selectedTwo: function() {
            if (this.twoSelected === false) {
                this.twoSelected = true;
                this.oneSelected = false;
                this.threeSelected = false;
            } else {
                this.twoSelected = false;
            }
        },

        selectedThree: function() {
            if (this.threeSelected === false) {
                this.threeSelected = true;
                this.twoSelected = false;
                this.oneSelected = false;
            } else {
                this.threeSelected = false;
            }
        },
    }
}
</script>

<style scoped>
    .selected {
        border: 2px solid #2F3241!important;
    }

    .pageWrapper {
        display: flex;
        align-items: center;
        flex-direction: column;
    }

    .sectionName {
        margin-top: 150px;
    }

    .alignCenter {
        display: flex;
        justify-content: space-around;
        align-items: center;
        width: 850px;
    }

    .optionBox {
        width: 270px;
        height: 525px;
        display: flex;
        justify-content: space-around;
        align-items: center;
        flex-direction: column;
        border: 2px solid lightgray;
    }

    .title {
        margin-bottom: 20px;
        font-size: 30px;
    }

    .subtitle {
        font-size: 20px;
    }

    .description {
        width: 150px;
    }

    .price {
        font-size: 30px;
    }

    .selectedButton {
        margin-top: 20px;
        background-color: #2F3241;
        color: #9FEAF9;
        text-transform: uppercase;
        padding: 10px;
        border-radius: 5px;
        border: 1px solid white;
    }

    .selectedButton:hover {
        cursor: pointer;
    }
</style>

