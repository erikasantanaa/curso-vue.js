<template>
<div id="desafio">
    <!-- 1) Exiba um alert quando o botão for clicado -->
    <div>
        <button v-on:click="alerta">Exibir Alerta</button>
    </div>
    
    <!-- 2) Escute o evento "keydown" e armazene o valor na propriedade
        data (dica: event.target.value) -->
    <div>
        <input type="text" v-on:keyup="valor = $event.target.value">
        <p>{{ valor }}</p>
    </div>
    
    <!-- 3) Ajuste o exemplo 2 para disparar o evento "keydown" somente
        quando a tecla for ENTER -->
    <div>
        <input type="text" v-on:keydown.enter=" alterarValor">
        <p>{{ valor }}</p>
    </div>
</div>
</template>
<script>
new Vue({
    el: '#desafio',
    data: {
        valor: ''
    },
    methods: {
        alerta() {
            alert('Alerta de desafio 02')
        },
        alterarValor(event) {
            this.valor = event.target.value
        }
    }
})
</script>