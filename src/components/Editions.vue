<template>
    <div class="pageWrapper">

        <h1 class="sectionName">Which Edition?</h1>

        <div class="alignCenter">
            <div class="optionBox" v-bind:class="{ 'selected' : standardSelected }">
                <div>
                    <div class="title">Standard</div>
                </div>
                <div>
                    <div class="description">
                     Lorem ipsum dolor, sit amet consectetur adipisicing elit. Laboriosam, sequi tenetur delectus omnis quia magnam minus vero soluta fuga optio.
                    </div>
                </div>
                <div>
                    <div class="price">$150</div>
                    <div class="description">Per User Per Year</div>
                    <div class="selectedButton" v-on:click="selectedStandard">Select</div>
                </div>
            </div>

            <div class="optionBox" v-bind:class="{ 'selected' : proSelected }">
                <div>
                    <div class="title">Pro</div>
                    <div class="subtitle">All of Standard +</div>
                </div>
                <div>
                    <div class="description">
                     Lorem ipsum dolor, sit amet consectetur adipisicing elit. Laboriosam, sequi tenetur delectus omnis quia magnam minus vero soluta fuga optio.
                    </div>
                </div>
                <div>
                    <div class="price">$300</div>
                    <div class="description">Per User Per Year</div>
                    <div class="selectedButton" v-on:click="selectedPro">Select</div>
                </div>
            </div>

            <div class="optionBox" v-bind:class="{ 'selected' : enterpriseSelected }">
                <div>
                    <div class="title">Enterprise</div>
                    <div class="subtitle">All of Pro +</div>
                </div>
                <div>
                    <div class="description">
                     Lorem ipsum dolor, sit amet consectetur adipisicing elit. Laboriosam, sequi tenetur delectus omnis quia magnam minus vero soluta fuga optio.
                    </div>
                </div>
                <div>
                    <div class="price">$600</div>
                    <div class="description">Per User Per Year</div>
                    <div class="selectedButton" v-on:click="selectedEnterprise">Select</div>
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
        }
    },


    methods: {
        selectedStandard: function() {
            if (this.standardSelected === false) {
                this.standardSelected = true;
            } else {
                this.standardSelected = false;
            }
        },

        selectedPro: function() {
            if (this.proSelected === false) {
                this.proSelected = true;
            } else {
                this.proSelected = false;
            }
        },

        selectedEnterprise: function() {
            if (this.enterpriseSelected === false) {
                this.enterpriseSelected = true;
            } else {
                this.enterpriseSelected = false;
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

