<template>
    <div class="calculator">
        <div class="display">{{current || 0}}</div>
            <div @click= "Clear" class="btn AC">AC</div>
            <div @click="Sign" class="btn">+/-</div>
            <div @click="Percentage" class="btn">%</div>
            <div @click="divide" class="btn operator ">/</div>
            <div @click="addDigit('7')" class="btn">7</div>
            <div @click="addDigit('8')" class="btn">8</div>
            <div @click="addDigit('9')" class="btn">9</div>
            <div @click="multiply" class="btn operator">x</div>
            <div @click="addDigit('4')" class="btn">4</div>
            <div @click="addDigit('5')" class="btn">5</div>
            <div @click="addDigit('6')" class="btn">6</div>
            <div @click="sub" class="btn operator">-</div>
            <div @click="addDigit('1')" class="btn">1</div>
            <div @click="addDigit('2')" class="btn">2</div>
            <div @click="addDigit('3')" class="btn">3</div>
            <div @click="add" class="btn operator">+</div>
            <div @click="addDigit('0')" class="btn zero">0</div>
            <div @click="Dot" class="btn">.</div>
            <div @click="equal" class="btn operator">=</div>

    </div>
</template>

<script>

    //import {mapGetters, mapState, mapMutations} from 'vuex'

    export default {
        name: 'Calculator',
        data(){
            return {
                current : '',
                previous: null,
                operator: null,
                operatorClicked: false
            }
        },

        methods: {

            // clear the inputs method
            Clear() {
                this.current = ''
            },

            // add or remove - sign to the integer
            Sign(){
                if(this.current.charAt(0) === '-'){
                    this.current = this.current.slice(1)
                } else {
                    this.current = `-${this.current}`
                }
                // the above condition can also be written as
                // this.current = this.current.charAt(0) === '-' ? this.current.slice(1) : `-${this.current}`
            },
            Percentage(){
                this.current = `${parseFloat(this.current) / 100}`
            },

            addDigit(number) {
                if(this.operatorClicked){
                    this.current = ''
                    this.operatorClicked = false
                }
              this.current += number

            },

            Dot(){

            },

            setStateValues(){
                this.previous = this.current
                this.operatorClicked = true
            },

            divide(){
                this.operator = (a,b) => a / b
                this.setStateValues()
            },

            multiply(){
                this.operator = (a,b) => a * b
                this.setStateValues()
            },

            sub() {
                this.operator = (a,b) => a - b
                this.setStateValues()
            },

            add(){
                this.operator = (a,b) => a + b
                this.setStateValues()

            },

            equal(){
                   this.current = this.operator(
                       parseFloat(this.current),
                       parseFloat(this.previous)
                   )
                this.previous = null
            }
        }


    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

    .calculator {
        display: grid;
        font-size: 25px;
        grid-template-columns: repeat(4, 1fr);
        grid-auto-rows: minmax(50px, auto);
        border: 1px solid lightgrey;
        border-radius: 3px;
    }

    .display {
        grid-column: 1/5;
        display: flex;
        justify-content: flex-end;
        align-items: center;
        background-color: darkgray;
        padding: 20px 5px 0 0;
        height: 52px;
    }



    .zero {
        grid-column: 1/3;
    }

    .btn {
        display: flex;
        justify-content: center;
        align-items: center;
        border: 1px solid lightgrey;
        cursor: pointer;
    }

    .operator {
        background-color: #f89733;
        color: azure;
    }

</style>
