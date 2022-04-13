<template>
  <div>
    <h1 :style="{ textDecoration }">hello {{ name }}</h1>
    <input type="text" v-model="name" />
    <br />
    <a :href="link">Link Google</a>
  </div>
</template>

<script>
export default {
  data: () => ({
    name: "Erika",
    textDecoration: "underline",
    link: "https://www.google.com.br/",
  }),
};
</script>