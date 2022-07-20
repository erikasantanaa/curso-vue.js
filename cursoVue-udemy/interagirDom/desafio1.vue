<template>
<!--desafio template 1-->
    <div id="desafio">
        <!-- 1) Preencha a tag <p> abaixo com o seu Nome e Idade - usando Interpolação -->
        <p>Usando VueJS - Meu nome é {{ nome }}, tenho {{idade}} anos.</p>
        
        <!-- 2) Exiba sua idade multiplicada por 3 -->
        <p>{{ idade * 3 }}</p>
        <p>{{idadeMult}}</p>
        
        <!-- 3) Chame uma função para exibir um número randomico
            entre 0 and 1 (Math.random()) -->
        <p>{{ Math.random()}}  {{random()}}</p>
        
        <!-- 4) Procure uma imagem no google e exiba na tag img 
            fazendo o binding no atributo "src" -->
        <div>
            <img :src="imagem" height="100">
        </div>
        
        <!-- 5) Inicialize o input com o seu nome (use o atributo "value") -->
        <div>
            <input type="text" :value="nome">
        </div>
    </div>
</template>

<script>
new Vue({
    el: '#desafio',
    data: {
        nome: 'Erika',
        idade: '29',
        imagem: 'http://files.cod3r.com.br/curso-vue/vue.jpg'
    },
    methods: {
        idadeMult: function() {
           return this.idade * 3
        },
        random() {
            return Math.random()
        }

    }
})
</script>
