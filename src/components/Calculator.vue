<template>
    <div class="calculator">
        <div class="display">123</div>
            <div class="btn AC">AC</div>
            <div class="btn">%</div>
            <div class="btn">/</div>
            <div class="btn">7</div>
            <div class="btn">8</div>
            <div class="btn">9</div>
            <div class="btn">x</div>
            <div class="btn">4</div>
            <div class="btn">5</div>
            <div class="btn">6</div>
            <div class="btn">-</div>
            <div class="btn">1</div>
            <div class="btn">2</div>
            <div class="btn">3</div>
            <div class="btn">+</div>
            <div class="btn zero">0</div>
            <div class="btn">.</div>
            <div class="btn">=</div>

    </div>
</template>

<script>

    //import {mapGetters, mapState, mapMutations} from 'vuex'

    export default {
        name: 'Calculator',


    }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

    .calculator {
        display: grid;
        font-size: 30px;
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
    }

    .AC {
        grid-column: 1/3;

    }

    .zero {
        grid-column: 1/3;
    }

    .btn {
        display: flex;
        justify-content: center;
        align-items: center;
        border: 1px solid lightgrey;
    }

</style>
