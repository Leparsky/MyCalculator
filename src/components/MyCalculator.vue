<template >
    <div class="calculator">
        <h1>Калякулятор</h1>
        <Table> 
            <div class="calc">
                <div class="calc-screen">
                    <p>0</p>
                </div>
                <div class="buttons">
                    <div class="btn ac bg-grey">ac</div>
                    <div class="btn percent bg-grey">%</div>
                    <div class="btn plus-minus bg-grey">+/-</div>
                    <div class="btn division bg-orange">/</div>
                    
                    <div class="btn seven">7</div>
                    <div class="btn eight">8</div>
                    <div class="btn nine">9</div>
                    <div class="btn multiply bg-orange">*</div>
                    
                    <div class="btn four">4</div>
                    <div class="btn five">5</div>
                    <div class="btn six">6</div>
                    <div class="btn minus bg-orange">-</div>
                    
                    <div class="btn one">1</div>
                    <div class="btn two">2</div>
                    <div class="btn three">3 </div>
                    <div class="btn plus bg-orange">+</div>
                    
                    <div class="btn zero">0</div>
                    <div class="btn dot">.</div>
                    <div class="btn eqal bg-orange">=</div>
                    
                </div>
            </div>
        </Table>
    </div>
</template>
<script>
export default {
    
}
</script>
<style>
    .calc {
        margin: 50px auto;
        width: 300px;
        height: 500px;
        /*border: 1px solid #000;*/
        border-radius: 20px;
        background: #000;
        color: #fff;
        font-family: Arial;
        padding: 18px;
        box-shadow: 4px 4px 4px #4f4f4f ;
    }
    .calc-screen {
        height: 125px;
        padding: 10;
        display: grid;
        justify-items: end;  
        align-items: end; 
        margin-bottom: 20px;
       }
       .calc-screen p {
        font-size: 3rem;
        text-align: right;
        margin: 0;
       }

    .buttons {
        display:  grid;
        grid-template-areas: 
        "ac plus-minus percent division"
        "seven eight nine multiply"
        "four five six minus"
        "one two three plus"
        "zero zero dot equal";
        grid-gap: 7px;
        justify-items: center;
    }

    .btn {
        width: 60px;
        height:  60px;
        background: #333;
        border-radius: 35%;
        text-align: center;
        line-height: 60px;
        font-size: 1.5rem;   
        cursor: pointer;
        user-select: none;
    }
    .btn.zero {
        grid-area: zero;
        width: 100%;
        border-radius: 20Px;
    }
    .btn:hover {
        filter: brightness(140%);
    }
    .btn:active {
        filter: brightness(80%);
    }
    .btn.bg-grey {
        background: #a6a6a6;
    }
    .btn.bg-orange {
        background: #ff9501;
    }


</style>
