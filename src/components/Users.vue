<template>
    <div class="pageWrapper">

        <h1 class="sectionName">How Many Users?</h1>

        <div class="alignCenter">
            <div>
                <div class="title">Number of Users:</div>
                <div id="input">
                    <div id="subtract" v-on:click="decrementUsers">-</div>
                    <div id="counter">{{ userCount }}</div>
                    <div id="add" v-on:click="incrementUsers">+</div>
                </div>
            </div>
            <div id="discount">
                <div id="title2">Save <span id="save">10%</span> when you upgrade to <span id="numOfLicense">6 licenses</span></div>
                <div id="upgrade" v-on:click="upgradeLicense">Upgrade to 6 licenses</div>
            </div>
        </div>

    </div>

        
</template>


<script>
export default {
    name: "Users",

    data: function() {
        return {
            userCount: 1,
        }
    },

    methods: {

        upgradeLicense: function() {
            this.userCount = 6;
            if (this.userCount >= 6) {
                document.getElementById('upgrade').style.display = "none";
                document.getElementById('title2').innerHTML = "You now have 10% discount!";
            }
        },

        incrementUsers: function() {
            this.userCount++;
            if (this.userCount >= 6) {
                document.getElementById('upgrade').style.display = "none";
                document.getElementById('title2').innerHTML = "You now have 10% discount!";
            }
        },

        decrementUsers: function() {
            if (this.userCount < 2) {
                return;
            } else {
                this.userCount--;
            }

            if (this.userCount < 6) {
                document.getElementById('upgrade').style.display = "block";
                document.getElementById('title2').innerHTML = 'Save <span id="save">10%</span> when you upgrade to <span id="numOfLicence">6 licences</span>';
            }
        }
    },
}
</script>

<style scoped>
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

    .title {
        font-size: 20px;
    }

    #title2 {
        font-size: 20px;
    }

    #input {
        display: flex;
        justify-content: space-around;
        align-items: center;
        width: 290px;
        border: 1px solid #2F3241;
        height: 90px;
    }

    #subtract {
        border: 1px solid #2F3241;
        padding-left: 15px;
        padding-right: 15px;
        font-size: 30px;
    }

    #subtract:hover, #add:hover {
        cursor: pointer;
        background-color: #2F3241;
        color: white;
    }

    #counter {
        font-size: 30px;
    }

    #add {
        border: 1px solid #2F3241;
        padding-left: 15px;
        padding-right: 15px;
        font-size: 30px;
    }

    #discount {
        width: 290px;
    }

    #numOfLicense {
        font-weight: bold;
    }

    #upgrade {
        text-transform: uppercase;
        font-size: 15px;
        background-color: #2F3241;
        color: white;
        padding: 15px;
        border-radius: 7px;
    }

    #upgrade:hover {
        color: #9FEAF9;
        cursor: pointer;
    }
</style>

