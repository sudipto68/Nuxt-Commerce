<script setup>
import "vue3-carousel/carousel.css";
import { Carousel, Slide, Pagination, Navigation } from "vue3-carousel";
import img1 from "~/assets/images/img1.webp";
import img2 from "~/assets/images/img2.webp";
import img3 from "~/assets/images/img3.webp";

const carouselConfig = {
  itemsToShow: 1,
  transition: 1000,
  touchDrag: true,
  autoPlay: true,
};

const sliderItems = [
  {
    id: 1,
    caption: "All the Latest Product In One Place",
    img: img1,
  },
  {
    id: 2,
    caption: "Grab the Latest Product",
    img: img2,
  },
  {
    id: 3,
    caption: "Find All Your Needs In One Place",
    img: img3,
  },
];
</script>

<template>
  <div class="w-full">
    <Carousel v-bind="carouselConfig" class="w-full">
      <Slide v-for="slide in sliderItems" :key="slide.id" class="w-full">
        <section
          class="w-full min-h-[80vh] flex items-center justify-center bg-center bg-cover bg-no-repeat"
          :style="{ backgroundImage: `url(${slide.img})` }"
        >
          <div class="flex-col">
            <p class="text-white text-4xl font-bold bg-opacity-50 p-4">
              {{ slide.caption }}
            </p>
            <p class="text-white text-lg">
              A single place for all your products. Discover more products on
              our products secion
            </p>
          </div>
        </section>
      </Slide>

      <template #addons>
        <Pagination />
      </template>
    </Carousel>
  </div>
</template>
<style scoped>
:deep(.carousel__pagination-button--active::after) {
  background-color: #ffff;
}

:deep(.carousel__pagination-button::after) {
  width: 10px;
  height: 10px;
  border-radius: 50%;
  border: 1px solid #ccc;
}
</style>
