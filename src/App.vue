<template>
  <div>
    <h1>{{ titulo }}</h1>
    <ul>
      <li v-for="foto of fotos" :key="foto">
        <img :src="foto.url" :alt="foto.titulo" />
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  data() {
    return {
      titulo: "AluraPic",
      fotos: [
        {
          url:
            "https://matsudapet.com.br/blog/wp-content/uploads/2019/08/shutterstock_559799125-compressed.jpg",
          titulo: "cachorro-fofo",
        },
        {
          url: "https://bsp.org.br/wp-content/uploads/2015/10/c%C3%A3o1.jpg",
          titulo: "cachorrinho",
        },
      ],
    };
  },
};
</script>

<style>
</style>
