<template>
    <div class="bar">
        <div id="navigation">
            <div class="logo"><i class="fab fa-cloudversify"></i></div>
            <ul class="nav">
                <li><a href="">Home</a></li>
                <li><a href="">Info</a></li>
                <li><a href="">Contact</a></li>
            </ul>
        </div>
    </div>
</template>



<script>
export default {
    name: "Navigation",

}
</script>

<style scoped>
    .bar {
        width: 100%;
        height: 70px;
        background-color: #2F3241;
        top: 0px;
        position: sticky;
        display: flex;
        align-items: center;
        justify-content: center;
        color: #9FEAF9;
    }

    #navigation {
        width: 100%;
        display: flex;
        align-items: center;
        margin-left: 20%;
    }

    .logo svg {
        width: 90px;
        height: 40px;
    }

    .nav {
        display: flex;
        justify-content: space-between;
        align-items: center;
        width: 300px;
        list-style-type: none;
        margin-left: 10%;
        font-family: 'Russo One', sans-serif;
    }

    a {
        text-decoration: none;
        color: inherit;
        text-transform: uppercase;
    }


</style>


