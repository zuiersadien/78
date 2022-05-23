<script setup lang="ts">
import {defineProps ,defineEmits} from "vue"

const props =defineProps(
    {
        valor:[Number,String],
        valorComas:String
    }
)

 const emit=defineEmits(["AumentarCripto"])
 

function emitFiatAmount(e){

    let TotalDevengado = e.target.value.replace(/,/g, "");
    
            emit('AumentarCripto',TotalDevengado)
        }
   

function filterKey(e) {
    let code=e.keyCode
    // Si el código es menor que 48 (0) o mayor que 57 (9)
    let especiales=[8,37,38,190]
    let numeros=[48,49,50,51,52,53,54,55,56,57,8,37,38,39,190]
    let verdad=numeros.some((numero)=>numero===code)

    console.log(code)
    if(verdad) {
    console.log(verdad)

    }else{
  e.preventDefault();
    }
    
  
   
}
</script>



<template>
        fiat
    <input type="text"
    v-model="valorComas"
    @keydown="filterKey"
    v-on:keyup="emitFiatAmount"
    maxlength="12"
    >


</template>