<template>
  <div class="bg-white">
    <div class="mx-auto max-w-2xl my-5 rounded-md py-3 px-4 sm:py-24 sm:px-6 lg:max-w-7xl lg:px-8 bg-zinc-100">
      <h2 class="text-2xl font-bold tracking-tight text-gray-900">New release</h2>

      <div class="mt-6 grid grid-cols-1 gap-y-10 gap-x-6 sm:grid-cols-2 lg:grid-cols-4 xl:gap-x-8">
        <div v-for="product in products" :key="product.id" class="group relative grid justify-center" v-show="product.release_date == 'new'">
          <div class="min-h-100 aspect-w-1 aspect-h-1 w-60 overflow-hidden rounded-md bg-gray-200 group-hover:opacity-75 lg:aspect-none lg:h-90">
            <img :src="product.imageSrc" :alt="product.imageAlt" class="h-full w-full object-cover object-center lg:h-full lg:w-full" />
          </div>
          <div class="mt-4 flex justify-between">
            <div>
              <h3 class="text-sm text-gray-700">
                <a :href="product.href">
                  <span aria-hidden="true" class="absolute inset-0" />
                  {{ product.name }}
                </a>
              </h3>
              <p class="mt-1 text-sm text-gray-500">{{ product.color }}</p>
            </div>
            <p class="text-sm font-medium text-gray-900">{{ product.price }}</p>
          </div>


          
          <!-- button increment -->
          <button class="bg-indigo-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded z-40" @click="add(product)">
            Button
          </button>
        </div>
      </div>
    </div>
  </div>
</template>
<script>
import Manga from "../data/book.js"
export default {
  name: 'MainitemList',
  props:{
    add:Function
  },
  data(){
    return{
      amount: 1,
      products: Manga
    }
  }
}
</script>
