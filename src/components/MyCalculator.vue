<template >
    <div class="calculator">
        <h1>Калякулятор</h1>
        <Table> 
            <div class="calc">
                <div class="calc-screen">
                    <p>{{inputValue}}</p>
                </div>
                <div class="buttons">
                    <div @click="ac" class="btn ac bg-grey">ac</div>
                    <div @click="operation('%')" class="btn percent bg-grey">%</div>
                    <div class="btn plus-minus bg-grey">+/-</div>
                    <div class="btn division bg-orange">/</div>
                    
                    <div @click="addDigit('7')" class="btn seven">7</div>
                    <div @click="addDigit('8')" class="btn eight">8</div>
                    <div @click="addDigit('9')" class="btn nine">9</div>
                    <div @click="operation('*')" class="btn multiply bg-orange">*</div>
                    
                    <div @click="addDigit('4')" class="btn four">4</div>
                    <div @click="addDigit('5')" class="btn five">5</div>
                    <div @click="addDigit('6')" class="btn six">6</div>
                    <div @click="operation('-')" class="btn minus bg-orange">-</div>
                    
                    <div @click="addDigit('1')" class="btn one">1</div>
                    <div @click="addDigit('2')" class="btn two">2</div>
                    <div @click="addDigit('3')" class="btn three">3 </div>
                    <div @click="operation('+')" class="btn plus bg-orange">+</div>
                    
                    <div @click="addDigit('0')" class="btn zero">0</div>
                    <div @click="addDigit('.')" class="btn dot">.</div>
                    <div @click="operation('=')" class="btn eqal bg-orange">=</div>
                    
                </div>
            </div>
        </Table>
    </div>
</template>
<script>
export default 
{
    name : 'MyCalculator',
    data()
    {
        return{
        inputValue : '0',
        firstDigit : "",
        secondDigit : "",
        currentOperation : "",
        operationResult : "0",
        }
    },
    methods: 
    {
        addDigit(val) {
        
            if  (this.operationResult !== "0")
                {
                    this.inputValue="0";
                    this.operationResult="0";
                }    
            if (this.inputValue === "0") 
            {   if (val===".")
            {
                this.inputValue = "0.";
            } 
                else 
            {
                    this.inputValue = val
            }
              
        }
         else 
        {
            this.inputValue=this.inputValue+val;
        }   
        },
        
        ac() 
        {
            this.firstDigit = "";
            this.secondDigit = "";
            this.inputValue ="0";
            this.currentOperation = "";
            this.operationResult = "0"
        },
        operation(val) 
        {   //alert(val);
            if ((this.firstDigit==="")||(this.currentOperation === "="))
            {
                this.firstDigit=this.inputValue;
                this.inputValue="0"
                this.currentOperation=val;
                this.secondDigit = "";
            }
            else 
            {  
                if (this.secondDigit==="") 
                {
                    this.secondDigit =this.inputValue
                
                 if (this.currentOperation === "+")
                {   
                    this.inputValue = String(Number(this.firstDigit)+Number(this.secondDigit))
                }
                if (this.currentOperation === "-")
                { 
                    this.inputValue = String(Number(this.firstDigit)-Number(this.secondDigit))
                }
                if (this.currentOperation === "*")
                { 
                    this.inputValue = String(Number(this.firstDigit)*Number(this.secondDigit))
                }
                if (this.currentOperation === "/")
                { 
                    this.inputValue = String(Number(this.firstDigit)/Number(this.secondDigit))
                }
                if (this.currentOperation === "%")
                { 
                    this.inputValue = String(Number(this.firstDigit)/100*Number(this.secondDigit))
                }
                console.log(this.secondDigit);
                this.firstDigit=this.inputValue;
                this.operationResult=this.inputValue;
                this.secondDigit = ""
                this.currentOperation = val        
                
                }
            }
        }
        

    },
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
