<template>
  <div class="bg-white p-2 shadow rounded ">
    <img :src="imageSrc" alt="Product image" class="w-96 h-96 object-fill rounded-t">
    <div class="p-2">
      <h3 class="text-xl font-bold">{{ name }}</h3>
      <p class="text-lg mt-2">{{ description }}</p>
      <p class="text-2xl mt-2 font-bold">{{ price }}</p>
    </div>
    <nuxt-link
      :to="{
        path: '/productDetail',
        query: {
          name: name,
          description: description,
          price: price,
          imageSrc: imageSrc,
        },
      }"
      class="mt-4 bg-red-500 text-white py-2 px-4 rounded font-medium hover:bg-red-600"
    >
      Buy
    </nuxt-link>
  </div>
</template>

<script>
export default {
  name: 'ProductCard',
  props: {
    name: {
      type: String,
      required: true,
    },
    description: {
      type: String,
      required: true,
    },
    price: {
      type: String,
      required: true,
    },
    imageSrc: {
      type: String,
      required: true,
    },
  },
};
</script>