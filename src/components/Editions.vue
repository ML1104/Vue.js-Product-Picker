<template>
    <div class="pageWrapper">

        <h1 class="sectionName">Which Edition?</h1>

        <div class="alignCenter">
            <div class="optionBox" v-bind:class="{ 'selected' : standardSelected }" v-on:click="selectedStandard">
                <div>
                    <div class="title">Standard</div>
                </div>
                <div>
                    <div class="product">
                     Standard package containing the game engine
                    </div>
                </div>
                <div>
                    <div class="price">$150</div>
                    <div class="description">Per User Per Year</div>
                    <div class="selectedButton">Select</div>
                </div>
            </div>

            <div class="optionBox" v-bind:class="{ 'selected' : proSelected }" v-on:click="selectedPro">
                <div>
                    <div class="title">Pro</div>
                    <div class="subtitle">All of Standard +</div>
                </div>
                <div>
                    <div class="product">
                     Everything in standard package including additional plugins and resources
                    </div>
                </div>
                <div>
                    <div class="price">$300</div>
                    <div class="description">Per User Per Year</div>
                    <div class="selectedButton">Select</div>
                </div>
            </div>

            <div class="optionBox" v-bind:class="{ 'selected' : enterpriseSelected }" v-on:click="selectedEnterprise">
                <div>
                    <div class="title">Enterprise</div>
                    <div class="subtitle">All of Pro +</div>
                </div>
                <div>
                    <div class="product">
                     Everything in pro package including maximum optimization and resources, as well as a step-by-step guide
                    </div>
                </div>
                <div>
                    <div class="price">$600</div>
                    <div class="description">Per User Per Year</div>
                    <div class="selectedButton">Select</div>
                </div>
            </div>
        </div>

    </div>

        
</template>


<script>
export default {
    name: "Editions",

    data: function() {
        return {
            standardSelected: false,
            proSelected: false,
            enterpriseSelected: false,

            editions: [
                "standard",
                "Pro",
                "Enterprise"
            ]
        }
    },


    methods: {
        selectedStandard: function() {
            if (this.standardSelected === false) {
                this.standardSelected = true;
                this.proSelected = false;
                this.enterpriseSelected = false;
                this.$emit('selectStandardEdition');
            }
        },

        selectedPro: function() {
            if (this.proSelected === false) {
                this.proSelected = true;
                this.standardSelected = false;
                this.enterpriseSelected = false;
                this.$emit('selectProEdition');
            }
        },

        selectedEnterprise: function() {
            if (this.enterpriseSelected === false) {
                this.enterpriseSelected = true;
                this.proSelected = false;
                this.standardSelected = false;
                this.$emit('selectEnterpriseEdition');
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

    .product {
        width: 150px;
        height: 100px;
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

    .optionBox:hover {
        cursor: pointer;
    }
</style>

