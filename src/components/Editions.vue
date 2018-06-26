<template>
    <div class="pageWrapper">

        <h1 class="sectionName">Which Edition?</h1>

        <div class="alignCenter">
            <div class="optionBox">
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
                    <div class="selectedButton">Select</div>
                </div>
            </div>

            <div class="optionBox">
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
                    <div class="selectedButton">Select</div>
                </div>
            </div>

            <div class="optionBox">
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
                    <div class="selectedButton">Select</div>
                </div>
            </div>
        </div>

    </div>

        
</template>


<script>
export default {
    name: "Editions"
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

