<script setup lang="ts">
import {defineProps ,defineEmits} from "vue"

const props =defineProps(
    {
        cripto:[Number,String]
    }
)

 const emit=defineEmits(["AumentarValor"])
 

function emitFiatAmount(e){
            let numero=Number(e.target.value)
            emit('AumentarValor', numero)
          
        }



</script>



<template>
    <input type="number"
    v-model="cripto"
    @keyup="emitFiatAmount"
    >


</template>