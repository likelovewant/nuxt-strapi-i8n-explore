<template>
  <div>
    <Nav class="sticky top-0" />
    <h1 class="font-bold m-5 md:mx-10">
      {{ currentProduct.name }}
    </h1>
    <Products :data="currentProduct" />
    <Ads class="mx-auto sm:m-10" />
    <Footer />
  </div>
</template>

<script>
export default {
  async asyncData({ $strapi, i18n,route }) {
    const slug = route.params.products
    const currentProduct = await $strapi.findOne('products',{slug,locale:i18n.locale} )
    return { currentProduct }
  },
  data() {
    return {
      currentProduct: {},
    }
  },
}
</script>

<style scoped></style>
