<template>
  <div>
    <div v-for="square of squares" :key="square.id" class="square"  :class="{'green': square.clicked, 'row': square.newRow}" @click="clickSquare(square)">
    </div>
  </div>
</template>

<script>
export default {
    name: 'FollowMe',
    data() {
        return {
            squares: [{
                id: 1,
                clicked: false
            }, 
            {
                id: 2,
                clicked: false
            }, 
            {
                id: 3,
                clicked: false
            }, 
            {
                id: 4,
                clicked: false,
                newRow: true
            }, 
            {
                id: 5,
                clicked: false,
                newRow: true
            }, 
            {
                id: 6,
                clicked: false
            }, 
            {
                id: 7,
                clicked: false
            }],
            clickedSquares: [],
            interval: null
        }
    },
    methods: {
        clickSquare(square) {
            square.clicked = true
            if(this.clickedSquares.indexOf(square.id) == -1) {
                this.clickedSquares.push(square.id)
            }

            if(this.clickedSquares.length == this.squares.length) {
                this.changeToWhite()
            }
        },
        changeToWhite() {
            this.interval = setInterval(() => {
                let currentSquareId =  this.clickedSquares.pop()
                this.squares.find(square => square.id == currentSquareId).clicked = false
                if(this.clickedSquares.length == 0) {
                    clearInterval(this.interval);
                }
            }, 1000);

        }
    }
}
</script>

<style>
.square {
    float: left;
    width: 30px;
    height: 30px;
    border: 1px solid #000;
    margin-right: 5px;
    margin-bottom: 5px;
    background: white;
}

.green {
    background: green;
}

.row {
    clear: left;
}
</style>