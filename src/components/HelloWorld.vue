<script setup lang="ts">
import { ref} from 'vue'
import Cripto from "./Cripto.vue"
import Fiat from "./Fiat.vue"

const valor=ref(0)
const cripto=ref(0)
const valorComas=ref("")
const criptoComas=ref("")

function AumentarCripto(val){
    valor.value=val
    cripto.value=valor.value*2
    console.log(valor.value)
    ComasenValor(val)
  
}

function AumentarValor(val){
    cripto.value=val
    valor.value=cripto.value/2  
    ComasenValor(valor.value)

}
function ComasenValor(val){

let internationalNumberFormat = new Intl.NumberFormat('en-US')
     valorComas.value =internationalNumberFormat.format(val)
  console.log(valorComas.value)
}
</script>

<template>
  <Cripto
  :cripto="cripto"
  @AumentarValor="AumentarValor"
  />



  <Fiat
  :valor="valor"
  @AumentarCripto="AumentarCripto"
  :valorComas="valorComas"
  />




</template>

<style scoped>
a {
  color: #42b983;
}

label {
  margin: 0 0.5em;
  font-weight: bold;
}

code {
  background-color: #eee;
  padding: 2px 4px;
  border-radius: 4px;
  color: #304455;
}
</style>
