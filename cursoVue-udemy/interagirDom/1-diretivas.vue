<template>
<!-- this , {{}}, v-bind, v-once, v-html,-->
  <div id="app">
      <p v-once>{{ titulo }}</p>
      <p>{{ saudacao }}</p>
      <a :href="link">Google</a>
      <hr>
      <p v-html="linkHtml"></p>
  </div>
</template>

<script>
    new Vue({
        el: '#app',
        data: {
            titulo: 'usando vue',
            link: 'http://google.com.br',
            linkHtml: '<a href="http://google.com.br">'
        },
        methods: {
            saudacao: function() {
                this.titulo = 'Bom Dia!!'
                return this.titulo
            }
        }
    })
</script>
