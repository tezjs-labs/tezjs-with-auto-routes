<script>
import { ProductList } from "../../../domain/product-list.ts";
export default {
  layoutName: "default",
  head: {
    title: "tezjs: starter vue project",
  },
  created() {},

  data() {
    return {
      productData: ProductList,
      img: 4,
    };
  },
  methods: {
    getProductImg(productName) {
      var finalDetails = this.productData.find(
        (x) => x.name.split(" ").join("").toLowerCase() == productName
      );
      return finalDetails.img;
    },
    getProductName(productName) {
      var finalDetails = this.productData.find(
        (x) => x.name.split(" ").join("").toLowerCase() == productName
      );
      return finalDetails.name;
    },
    getProductPrice(productName) {
      var finalDetails = this.productData.find(
        (x) => x.name.split(" ").join("").toLowerCase() == productName
      );
      return finalDetails.price;
    },
  },
};
</script>
<template>
  <headerComponent></headerComponent>
  <div class="bg-white">
    <div
      class="max-w-2xl mx-auto my-auto px-4 grid items-center grid-cols-1 gap-x-8 sm:px-6 lg:max-w-6xl lg:py-20 lg:grid-cols-2"
    >
      <div>
        <h2 class="text-3xl font-extrabold tracking-tight text-gray-900 sm:text-4xl">
          {{ getProductName($tezRoute.params["product-name"]) }}
        </h2>
        <h3 class="mt-4 text-2xl text-gray-700">
          {{ getProductPrice($tezRoute.params["product-name"]) }}
        </h3>

        <dl
          class="mt-16 grid grid-cols-1 gap-x-6 gap-y-10 sm:grid-cols-2 sm:gap-y-16 lg:gap-x-8"
        >
          <div class="border-t border-gray-200 pt-4">
            <dt class="font-medium text-gray-900">Origin</dt>
            <dd class="mt-2 text-sm text-gray-500">Designed by Good Goods, Inc.</dd>
          </div>

          <div class="border-t border-gray-200 pt-4">
            <dt class="font-medium text-gray-900">Material</dt>
            <dd class="mt-2 text-sm text-gray-500">
              Solid walnut base with rare earth magnets and powder coated steel card cover
            </dd>
          </div>

          <div class="border-t border-gray-200 pt-4">
            <dt class="font-medium text-gray-900">Dimensions</dt>
            <dd class="mt-2 text-sm text-gray-500">
              6.25&quot; x 3.55&quot; x 1.15&quot;
            </dd>
          </div>

          <div class="border-t border-gray-200 pt-4">
            <dt class="font-medium text-gray-900">Finish</dt>
            <dd class="mt-2 text-sm text-gray-500">
              Hand sanded and finished with natural oil
            </dd>
          </div>

          <div class="border-t border-gray-200 pt-4">
            <dt class="font-medium text-gray-900">Includes</dt>
            <dd class="mt-2 text-sm text-gray-500">Wood card tray and 3 refill packs</dd>
          </div>

          <div class="border-t border-gray-200 pt-4">
            <dt class="font-medium text-gray-900">Considerations</dt>
            <dd class="mt-2 text-sm text-gray-500">
              Made from natural materials. Grain and color vary with each item.
            </dd>
          </div>
        </dl>
      </div>
      <div class="grid grid-cols-2 grid-rows-2 gap-4 sm:gap-6 lg:gap-8">
        <img
          :src="getProductImg($tezRoute.params['product-name'])"
          alt="img"
          class="bg-gray-100 rounded-lg"
        />
        <img
          :src="getProductImg($tezRoute.params['product-name'])"
          alt="img"
          class="bg-gray-100 rounded-lg"
        />
        <img
          :src="getProductImg($tezRoute.params['product-name'])"
          alt="img"
          class="bg-gray-100 rounded-lg"
        />
        <img
          :src="getProductImg($tezRoute.params['product-name'])"
          alt="img"
          class="bg-gray-100 rounded-lg"
        />
      </div>
    </div>
  </div>
  <footerComponent></footerComponent>
</template>
