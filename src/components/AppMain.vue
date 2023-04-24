<script>
export default {
  data() {
    return {
        
  }
},

 components: {
},

methods: {
    cancel() {
        let screen = document.querySelector("#screen");
        screen.innerHTML = "";
    },

    sum() {
        let screen = document.querySelector("#screen");
        let calc = parseInt(screen.innerHTML);
        console.log(calc);
    },

    clickButton(event) {
        let screen = document.querySelector("#screen");

        screen.innerHTML += event.target.innerHTML;
        if(event.target.innerHTML == "C"){
            this.cancel();
        } else if( event.target.innerHTML == "="){
            this.sum();
        }
    }
},

mounted() {
    let buttons = document.querySelectorAll(".cell");
    for (let i = 0; i < buttons.length; i++) {
        buttons[i].addEventListener("click", this.clickButton);
    }
}


 }
</script>
<template>

    <div class="container" id="calculator">
        <div id="screen">
        </div>

        <div class="cell grey-button" @click="cancel()">C</div>
        <div class="cell grey-button">+ / -</div>
        <div class="cell grey-button">%</div>
        <div class="cell orange-button"></div>
        <div class="cell number">7</div>
        <div class="cell number">8</div>
        <div class="cell number">9</div>
        <div class="cell orange-button">x</div>
        <div class="cell number">4</div>
        <div class="cell number">5</div>
        <div class="cell number">6</div>
        <div class="cell orange-button">-</div>
        <div class="cell number">1</div>
        <div class="cell number">2</div>
        <div class="cell number">3</div>
        <div class="cell orange-button">+</div>
        <div class="cell number" id="zero">0</div>
        <div class="cell orange-button">.</div>
        <div class="cell orange-button">=</div>

    </div>
   
</template>

<style scoped lang="scss">

#calculator{
    max-width: 300px;
    min-height: 300px;

    display: flex;
    flex-flow: row wrap;
    justify-content: center;
    align-items: center;

    margin: 50px auto;
    padding: 10px;

    border-radius: 30px;

    gap: 10px;

    background-color: rgba(0, 0, 0, 0.89);

    #screen {
        width: 100%;
        height: 50px;

        border-radius: 15px;
        background-color: #fff;

        display: flex;
        justify-content: flex-end;
        align-items: center;
        flex-flow: row nowrap;
        padding: 3px 5px;

        font-size:40px;
        overflow: hidden;
    }

    .cell {
        width: calc(100% / 4 - 10px);
        height: 50px;
        border: 0.5px solid rgba(0, 0, 0, 0.402);

        display: flex;
        justify-content: center;
        align-items: center;

        border-radius: 40%;

        background-color: #333333;
        color: white;
        cursor: pointer;

        font-size: 20px;

        &.grey-button {
            background-color: #a5a5a5;
        }

        &.orange-button {
            background-color: #ef9a37;
        }

        #zero {
            flex-grow: 1;
        }

        &:hover {
            scale: 1.1;
            filter: brightness(120%);
        }
    }

    



}
</style>
