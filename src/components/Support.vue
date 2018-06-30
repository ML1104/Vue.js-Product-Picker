<template>
    <div class="pageWrapper">

        <h1 class="sectionName">Standard or Priority support?</h1>
        
        <div>Priority response time (1 business day)</div>
        <div>Telephone, VOIP and email support</div>
        <div>Valid for the entire license period (1, 2, or 3 years)</div>

        <p></p>

        <div class="alignCenter">
            <div class="optionBox" v-bind:class="{ 'selected' : need }" v-on:click="selectedNeed">
                <div>
                    <div class="title">I would like Priority Support</div>
                </div>
                <div>
                    <div class="description">
                     Over telephone, email or VOIP.
                    </div>
                    <p></p>
                    <div class="description">
                     Within initial 24 hours.
                    </div>
                </div>
                <div>
                    <div class="price">$149</div>
                    <div class="description">Per Year</div>
                    <div class="selectedButton">Select</div>
                </div>
            </div>

            <div class="optionBox" v-bind:class="{ 'selected' : needNot }" v-on:click="selectedNot">
                <div>
                    <div class="title">I don't need Priority Support</div>
                </div>
                <div>
                    <div class="description">
                     Over email only.
                    </div>
                    <p></p>
                    <div class="description">
                     Within 3 working days.
                    </div>
                </div>
                <div>
                    <div class="price">$0</div>
                    <div class="description">Per Year</div>
                    <div class="selectedButton">Select</div>
                </div>
            </div>
        </div>

        <br>
        <br>
        <br>
        <br>
        <br>
        <br>
        <br>
        <br>

    </div>

        
</template>


<script>
export default {
    name: "Support",

    data: function() {
        return {
            need: false,
            needNot: false,
        }
    },


    methods: {
        selectedNeed: function() {
            if (this.need === false) {
                this.need = true;
                this.needNot = false;
                this.$emit('prioritySupport')
            }
        },

        selectedNot: function() {
            if (this.needNot === false) {
                this.needNot = true;
                this.need = false;
                this.$emit('standardSupport')
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
        width: 350px;
        height: 525px;
        display: flex;
        justify-content: space-around;
        align-items: center;
        flex-direction: column;
        border: 2px solid lightgray;
    }

    .optionBox:hover {
        cursor: pointer;
    }

    .title {
        margin-bottom: 20px;
        font-size: 30px;
    }

    .subtitle {
        font-size: 20px;
    }

    .description {
        width: 250px;
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

