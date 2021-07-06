<template>
  <div>
    <div
      class="sm:grid sm:grid-cols-3 md:grid-cols-3 gap-6 justify-center items-center"
    >
      <div
        v-for="(product, i) in data"
        :key="i"
        class="flex flex-col max-h-screen shadow-xl m-8 sm:m-2 md:m-4 justify-center items-center"
      >
        <div class="img-wrapper h-3/4 mx-auto max-h-screen">
          <img
            class=" rounded-t-lg bg-white pt-2 pb-2"
            :src="`http://localhost:1337${product.Image[0].url}`"
            alt=""

          />
        </div>

        <div>
          <p class="text-center m-3">
            {{ product.Name }}
          </p>

          <NuxtLink :to="localePath({name: 'products-slug', params:{slug:product.slug}})">
            <button class="button--green mb-4">View Product</button>
          </NuxtLink>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// import axios from '@nuxtjs/axios'
export default {
  name: 'Featured',
  props: ['data'],
}
</script>

<style scoped>
/* img {
  height: 12em;
} */
.Img {
  max-height: 400px;
  max-width: 300px;

}
.container {
  margin: 0 auto;
  min-height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
  text-align: center;
}
</style>
