<template>
    <div class="pageWrapper">

        <h1 class="sectionName">How Many Users?</h1>

        <div class="alignCenter">
            <div>
                <div class="title">Number of Users:</div>
                <div id="input">
                    <div id="subtract">-</div>
                    <div id="counter">1</div>
                    <div id="add">+</div>
                </div>
            </div>
            <div>
                <div class="title">Save <span id="save">5%</span> when you upgrade to <span id="numOfLicence">6 licences</span></div>
                <div id="upgrade">Upgrade to 6 licences</div>
            </div>
        </div>

    </div>

        
</template>


<script>
export default {
    name: "Users"
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

    #numOfLicence {
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

