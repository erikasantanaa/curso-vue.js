<template>
  <!-- Interpolação (incluir js no {{aqui}} de maneira simples c/ uma linha), 
    -->
  <div id="app">
      <p>{{ contador > 10 ? 'Maior do que 10' : 'Menor do que 10' }}</p>
      <!-- <p>{{ contador + 2 }}</p> -->
      <button v-on:click="somar">Somar 1</button>
      
  </div>
</template>

<script>
    new Vue({
        el: '#app',
        data: {
            contador: 0,
        },
        methods: {
            somar() {
                this.contador++
            }
        }
    })
</script>

