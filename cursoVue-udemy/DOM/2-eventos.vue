<template>
  <!-- Eventos, obtendo dados eventos(v-on:click,v-on:mousemove,$event (palavra reservada),
  Modificadores de evento: stop (parar um comportamento)  prevent(previnir um comportamento),
    Eventos de teclado(v-on:keyup.enter),
    ), -->
  <div id="app">
      <p>{{ contador }}</p>
      <button v-on:click="somar(5, $event)">Somar 1</button>
      <p v-on:mousemove="atualizarXY">
        Mouse: {{ x }} e {{ y }}
        <span v-on:mousemove.stop>Parar Aqui</span>
      </p>
      <a v-on:click="naoNavegar" href="http://google.com">Google</a>
      <hr>
      <input type="text" v-on:keyup.enter="exibirAlerta">
  </div>
</template>

<script>
    new Vue({
        el: '#app',
        data: {
            contador: 0,
            x: 0,
            y: 0,
        },
        methods: {
            somar(passo, event) {
                console.log(passo, event)
                this.contador += passo
            },
            atualizarXY(event){
                this.x = event.clientX
                this.y = event.clientY
            },
            exibirAlerta() {
                alert('Estou te alertando')
            },
            //funçao mesmo comportamento stop e prevent
            // naoNavegar(event) {
            //     event.preventDefault()
            // }
            // parar(event){ 
            //     event.stopPropagation()
            }
        }
    })
</script>

