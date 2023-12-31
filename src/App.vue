<!-- script é o javaScript -->
<script setup>
import Notificacao from "./components/Notificacao.vue"
import Card from "./components/Card.vue"
import { ref } from 'vue';

// usando mascaras

const nome = "Maria"
const idade = 20
const aparece = true

// eventos 

function mostrarConsole(){
    console.log("olá Leném")
}

// reatividade

let frame = ref("Vue")
function alterarFr(){
    frame.value = 'React'
}

const contador = ref(0)
function add (){
    contador.value ++
}

// Atributos dinamicos 

const url = "https://upload.wikimedia.org/wikipedia/commons/f/f1/Vue.png"
const valorInicial = "Valor inicial"

// ligação bicondicional

const inputValor = ref('')
const numero2 = ref(0)
const numero1 = ref(0)
const mul = ref(0)
const dolar = ref(1)
const real = ref(4.85)

// if e else

const mostrar = ref(true)

// repetição

const linguagens = ["JAVA" , "JAVASCRIPT", "PHP"]
const cards = [
    {
        titulo : "Teste 1",
        conteudo: "OI OI OI"
    },
    {
        titulo : "Teste 2",
        conteudo: "BLA BLA BLA"
    },
    {
        titulo : "Teste 3",
        conteudo: "HI HI HI"
    }
]

</script>

<!-- template é o html -->
<template>
  <main>
    <h1>Curso de VUE 3 </h1>
  <hr>
  <h2>1. Usando máscaras</h2>
  <p> Meu nome é {{  idade > 17 && aparece ? nome : "(ops não posso mostrar)" }}, e minha idade é {{
   idade > 17 ? idade + " anos ": "(não posso revelar a idade) "  }} </p>
  <p>{{ idade >= 18 ? 'você é maior de idade': 'você é menor de idade' }}</p>

<hr>

 
<h2>2. Eventos</h2>

<button @click = "mostrarConsole"> 
    Clique aqui
</button>

<hr>


<h2>3. Reatividade</h2>
<p>Nosso framework é {{ frame }}</p>
<button @click="alterarFr">
    Alterar framework
</button>

<hr>
<p>Contador : {{ contador }}</p>
<button @mouseenter="add">
    Adicionar
</button>

<hr>

<h2>4. Atributos dinâmicos Com V-BIND</h2>
<img width = "100px" :src="url" alt="imagem do VUE JS">
<input :value = "valorInicial" type="text">

<hr>

<h2>5. Ligação bicondicional</h2>
<input v-model="inputValor" type="text">
<button @click="console.log(inputValor)">
    Mostrar valor
</button>
<p>{{ inputValor }}</p>

<hr>

<input v-model="numero1" type="number">
<input v-model="numero2" type="number">
<p>{{numero1}} X {{numero2}} = {{ numero1 * numero2 }}</p>

<hr>

<p>Digite um valor em dolar </p>
<input v-model="dolar" type="number">
<p>O valor em reais: R$ {{ (real * dolar).toFixed(2).toString().replace(".", ",") }}</p>

<hr>

<h2>6. Componentes </h2>
<Card titulo = "Primeiro Titulo" conteudo = "Lorem ipsum, dolor sit amet consectetur adipisicing elit. Cumque reprehenderit voluptatem omnis earum quisquam hic eaque non! Vero quam nihil dolorem unde dolor laborum harum, impedit praesentium quisquam autem esse."/>

<Card titulo = "Segundo Titulo" conteudo = "Lorem ipsum, dolor sit amet consectetur adipisicing elit."/>

<hr>

<h2>7. IF e ELSE</h2>

<button @click="mostrar = !mostrar">
    Esconde/mostra
</button>

<p v-if="mostrar">Aparece</p>
<p v-else> Some </p>
<p v-show="mostrar">texto surpresa</p>

<hr>
<h2>8. Estrutura de repetição </h2>

<p v-for="item in linguagens">{{ item }}</p>

<div v-for = "item in cards">
    <Card :titulo = "item.titulo"  :conteudo ="item.conteudo"/>
</div>

<hr>

<h2>9. Estilos scoped</h2>

<p> O estilo só vai servir para um só tipo de escopo, como por exemplo os cards, se eu quiser pegar o estilo dos cards e dar para outro escopo ele não vai aderir.</p>

<hr>

<h2>10. Classes dinâmicas</h2>

<Notificacao tipo="sucesso" texto = "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Veniam fugiat minus, cum incidunt, dolorum tempora exercitationem sit." />

<Notificacao tipo="falha" texto = "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Veniam fugiat minus, cum incidunt, dolorum tempora exercitationem sit." />

<Notificacao texto = "Lorem ipsum dolor sit amet consectetur, adipisicing elit. Veniam fugiat minus, cum incidunt, dolorum tempora exercitationem sit." />


  </main>
</template>

<!-- style é o css -->
<style scoped>
 *{
    font-family: Arial, Helvetica, sans-serif;
 }
    main{
        padding-bottom: 320px;
    }
 

</style>
