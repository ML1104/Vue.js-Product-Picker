<template>
    <div class="pageWrapper">

        <h1 class="sectionName">How Many Users?</h1>

        <div class="alignCenter">
            <div>
                <div class="title">Number of Users:</div>
                <div id="input">
                    <div id="subtract" v-on:click="decrementUsers">-</div>
                    <div id="counter">{{ users }}</div>
                    <div id="add" v-on:click="incrementUsers">+</div>
                </div>
            </div>
            <div id="discount">
                <div id="title2">Save <span id="save">10%</span> on your next purchase when you upgrade to <span id="numOfLicense">7 licenses</span></div>
                <div id="upgrade" v-on:click="upgradeLicense">Upgrade to 7 licenses</div>
            </div>
        </div>

    </div>

        
</template>


<script>
export default {
    name: "Users",

    props: {
        users: { required: true }
    },

    data: function() {
        return {
            
        }
    },

    mounted: function() {
        this.numOfUsers()             
    },

    methods: {
        addUsers: function() {
            this.$emit('addUser');
        },

        removeUsers: function() {
            this.$emit('removeUser');
        },

        numOfUsers: function() {
            this.$emit('userCount');
        },

        upgradeLicense: function() {
            this.users = 7;
            if (this.users >= 6) {
                document.getElementById('upgrade').style.display = "none";
                document.getElementById('title2').innerHTML = "You now have 10% discount on your next purchase!";
            }
        },

        incrementUsers: function() {
            this.$emit('addUser');
            if (this.users >= 6) {
                document.getElementById('upgrade').style.display = "none";
                document.getElementById('title2').innerHTML = "You now have 10% discount on your next purchase!";
            }
        },

        decrementUsers: function() {
            if (this.users < 2) {
                return;
            } else {
                this.$emit('removeUser');
            }

            if (this.users < 8) {
                document.getElementById('upgrade').style.display = "block";
                document.getElementById('title2').innerHTML = 'Save <span id="save">10%</span>on your next purchase when you upgrade to <span id="numOfLicence">7 licences</span>';
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

