<template>
<!-- Two-way-binding 
v-model: tem a sincronia dos daaos sem precisar do v-bind e v-on,
 propriedades computadas : o resultado computado tbm é uma função,mas é chamado como atributo no {{}},
 Monitoramento de mudanças  (watch): monitorar as mudanças em determinada variavel e 
 fazer algo em resposta a essas alterações.

 -->
  <div id="app">
      <p>{{ titulo }}</p>
      <input type="text" v-model="titulo">
      <hr>
      <button v-on:click="aumentar">Aumentar</button>
      <button v-on:click="contador2++">aumentar 2</button>
      <button v-on:click="diminuir">Diminuir</button>
      <p>Contador: {{ contador }} |  {{ contador2 }}</p>
      <p>Resutado: {{ resultado2}}</p>
  </div>
</template>

<script>
    new Vue({
        el: '#app',
        data: {
            titulo: 'Usando Vue!',
            contador: 0,
        },
        computed: {
            resultado2() {
                console.log('Metodo computed resultado chamado...')
                return this.resultado = this.contador >= 5 ?
                    'Maior ou igual a 5' : 'Menor que 5'
        },
        watch: {
            
        },
        methods: {
            aumentar() {
                this.contador++
            },
            diminuir() {
                this.contador--
            },
            resultado1() {
                console.log('Metodo resultado chamado...')
                return this.resultado = this.contador >= 5 ?
                    'Maior ou igual a 5' : 'Menor que 5'
            }
        }
    })
</script>
