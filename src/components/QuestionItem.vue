<template>

    <div class="question" >
        <h1> {{word.id}}) What do you mean by : {{word.question}}</h1>
      
    </div>
    <div>
        <ul class="option">
            <li>{{word.option[0]}}</li>
            <li>{{word.option[1]}}</li>
            <li>{{word.option[2]}}</li>
        </ul>
    </div>
    <div :class="hint">
        <button :class="hintClass" v-on:click="showHint()">
             Look for Hint
        </button>
        <h2> Hint : "{{word.hint}}"</h2>
    </div>

    <div class="buttondiv">
        <button :class="buttonClass" v-on:click="toggle(word)"> Show Answer
         
        </button>
    </div>

    <hr class="endLine">



</template>

<script>


export default{
    name: 'QuestionItem',
    props:{
        word: Array
    },

    data() {
        return{
            buttonClass : "text-green",
            hintClass : "btn-hint",
            hint: "hint "

        };
    },
   
    
    methods :{
        toggle(word){
            // this.buttonClass = 'text-red'
            const ans=word.answer
            // Create element:
// const para = document.createElement("p");
// this.para.innerHTML = book.option[ans];
// this.document.getElementById("mydiv").appendChild(para);
alert(word.option[ans])
         
        },
        showHint() {
            this.hint = 'hint2'

            this.hintClass = 'btn-hide'
        }
    }
   
}


</script>

<style scoped>

.endLine{
   margin-top: 40px;
    border: 1px solid #ae5dda;
}
.buttondiv {
    margin-top: -20px;
}
.btn-hide{
    display: none;
}
.btn-hint{
    /* display: none; */
    margin: 10px 0;
    padding: 20px;
    /* position: absolute; */
    /* top:50%; */
    display: block;
  width: 100%;
  border: none;
  /* background-color: #04AA6D; */
  background-image: linear-gradient(to right, #46345f 0%, #ae5dda 51%, #46345f 100%);
  padding: 14px 28px;
  font-size: 16px;
  cursor: pointer;
  border-radius: 15px;
  text-align: center;
  color: #e2d4f1;
  font-weight: 800;

}
.hint{
    grid-area: hint;
    background-color: #382a4b;
    padding: 10px;
    align-items: center;
    color: #382a4b;
}
.hint2{
    text-align: center;
    grid-area: hint;
    background-color: #493662;
    padding: 10px;
    margin-bottom: 30px;
    color: rgb(176, 169, 169);
}

.text-green {
    margin: 10px 0;
    padding: 20px;
    /* position: absolute; */
    /* top:50%; */
    display: block;
  width: 100%;
  border: none;
  /* background-color: #04AA6D; */
  background-image: linear-gradient(to right, #46345f 0%, #ae5dda 51%, #46345f 100%);
  padding: 14px 28px;
  font-size: 16px;
  cursor: pointer;
  border-radius: 15px;
  text-align: center;
  color: #e2d4f1;
  font-weight: 800;
    
}


h4{
    margin: 2px;
}
.option{
    background-color: #382a4b;
    font-size: 1.5em;
}
.option li{
    margin-left: 30%;
    padding: 10px;
    color: whitesmoke;
}



.question{
    padding: 20px;
    background-color: #382a4b;
    text-align: center;
    color: white;
    grid-area: question;
    
}

</style>