<template>
  <div class="rounded overflow-hidden shadow-lg bg-white md:flex">
    <!-- Image -->
    <img
      class="object-cover max-w-fit"
      src="https://www.demojuniper.com/handlers/imageRequest.ashx?path=68747470733a2f2f712d78782e627374617469632e636f6d2f78646174612f696d616765732f686f74656c2f6d61783530302f3335373437303535332e6a70673f6b3d39383830643062316139303234633337623233313132613134333065313437326161346131633563303664386163393233376261386338323466323930666636266f3d26733d3230303078&mediaSize=lg&imgSize=bigger&coded=1"
      alt="Hotel Image"
    />

    <!-- Card Content -->
    <div class="px-6 py-4">
      <!-- Title and Rating -->
      <div class="flex justify-between items-center">
        <h2 class="text-2xl font-bold">
          La Quinta Inn & Suites by Wyndham Houston - Magnolia
        </h2>
  
        <div
              v-for="rate in 3"
              :key="rate"
              :class="['text-4xl cursor-pointer', rate <= ratingStars ? 'text-yellow-400 ' : 'text-gray-300']"
              @click="setRatingStars(rate)"
            > ★</div>
      </div>

      <!-- Location -->
      <div to="/" class="text-xl text-gray-700 md:flex item-center pt-2 hover:cursor-pointer">
        <svg xmlns="http://www.w3.org/2000/svg" width="1em" height="1em" viewBox="0 0 24 24">
          <path fill="#888888" d="M12 4C9.24 4 7 6.24 7 9c0 2.85 2.92 7.21 5 9.88c2.11-2.69 5-7 5-9.88c0-2.76-2.24-5-5-5m0 7.5a2.5 2.5 0 0 1 0-5a2.5 2.5 0 0 1 0 5" opacity=".3"></path>
          <path fill="#888888" d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7M7 9c0-2.76 2.24-5 5-5s5 2.24 5 5c0 2.88-2.88 7.19-5 9.88C9.92 16.21 7 11.85 7 9"></path>
          <circle cx="12" cy="9" r="2.5" fill="#888888"></circle>
        </svg>
        <div class="border-b">The Woodlands (TX), Texas, United States-Map</div>
      </div>

      <!-- Rating and Review -->
      <div class="flex items-center mt-2">
        <div class="flex items-center">
          <div class="flex">
            <!-- Circle Rating - Dynamic -->
            <div
              v-for="index in 5"
              :key="index"
              :class="['rounded-full w-6 h-6 mr-1 cursor-pointer', index <= rating ? 'bg-teal-500' : 'bg-gray-300']"
              @click="setRating(index)"
            ></div>
          </div>
          <span class="ml-2 text-xl font-bold text-gray-600">{{ rating }} - {{ ratingDescription }}</span>
        </div>
      </div>

      <!-- Description -->
      <div class="md:flex justify-between">
        <p class="mt-2 font-serif text-gray-600 text-lg max-w-[60%]">
          Great care is taken to ensure guests experience comfort through top-notch services and amenities. Re...
        </p>
        <div class="text-lg font-semibold text-gray-800 item-center">
          <div>Best stay price </div>
          <div class="text-gray-900 text-xl font-bold flex items-center p-1">
            $818
            <svg class="p-0.5 ml-1" xmlns="http://www.w3.org/2000/svg" width="20" height="20" viewBox="0 0 50 50">
              <path fill="#888888" d="M41 1H9C6.8 1 5 2.8 5 5v40c0 2.2 1.8 4 4 4h32c2.2 0 4-1.8 4-4V5c0-2.2-1.8-4-4-4M17 41c0 1.1-.9 2-2 2h-4c-1.1 0-2-.9-2-2v-1c0-1.1.9-2 2-2h4c1.1 0 2 .9 2 2zm0-8c0 1.1-.9 2-2 2h-4c-1.1 0-2-.9-2-2v-1c0-1.1.9-2 2-2h4c1.1 0 2 .9 2 2zm0-8c0 1.1-.9 2-2 2h-4c-1.1 0-2-.9-2-2v-1c0-1.1.9-2 2-2h4c1.1 0 2 .9 2 2zm12 16c0 1.1-.9 2-2 2h-4c-1.1 0-2-.9-2-2v-1c0-1.1.9-2 2-2h4c1.1 0 2 .9 2 2zm0-8c0 1.1-.9 2-2 2h-4c-1.1 0-2-.9-2-2v-1c0-1.1.9-2 2-2h4c1.1 0 2 .9 2 2zm0-8c0 1.1-.9 2-2 2h-4c-1.1 0-2-.9-2-2v-1c0-1.1.9-2 2-2h4c1.1 0 2 .9 2 2zm12 16c0 1.1-.9 2-2 2h-4c-1.1 0-2-.9-2-2v-1c0-1.1.9-2 2-2h4c1.1 0 2 .9 2 2zm0-8c0 1.1-.9 2-2 2h-4c-1.1 0-2-.9-2-2v-1c0-1.1.9-2 2-2h4c1.1 0 2 .9 2 2zm0-8c0 1.1-.9 2-2 2h-4c-1.1 0-2-.9-2-2v-1c0-1.1.9-2 2-2h4c1.1 0 2 .9 2 2zm0-9c0 1.1-.9 2-2 2H11c-1.1 0-2-.9-2-2V8c0-1.1.9-2 2-2h28c1.1 0 2 .9 2 2z"/>
            </svg>
          </div>
        </div>
      </div>

      <div class="pr-2 mt-3 md:flex justify-between relative">
        <div class="flex ">
          <div class="btn-two">Info</div>
          <div class="btn-two">Compare</div>
          <div class="btn-two">
            <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24">
              <path fill="#888888" d="m12 21.35l-1.45-1.32C5.4 15.36 2 12.28 2 8.5C2 5.42 4.42 3 7.5 3c1.74 0 3.41.81 4.5 2.09C13.09 3.81 14.76 3 16.5 3C19.58 3 22 5.42 22 8.5c0 3.78-3.4 6.86-8.55 11.54z"/>
            </svg>
          </div>
          <div class="btn-two">
            <svg xmlns="http://www.w3.org/2000/svg" width="32" height="32" viewBox="0 0 24 24">
              <path fill="#888888" d="M18 16.08c-.76 0-1.44.3-1.96.77L8.91 12.7c.05-.23.09-.46.09-.7s-.04-.47-.09-.7l7.05-4.11c.54.5 1.25.81 2.04.81c1.66 0 3-1.34 3-3s-1.34-3-3-3s-3 1.34-3 3c0 .24.04.47.09.7L8.04 9.81C7.5 9.31 6.79 9 6 9c-1.66 0-3 1.34-3 3s1.34 3 3 3c.79 0 1.5-.31 2.04-.81l7.12 4.16c-.05.21-.08.43-.08.65c0 1.61 1.31 2.92 2.92 2.92c1.61 0 2.92-1.31 2.92-2.92s-1.31-2.92-2.92-2.92"/>
            </svg>
          </div>
        </div>
        <div>
          <button class="bg-gray-900 absolute hover:bg-gray-500 text-white font-bold py-3 px-4 rounded  right-0 bottom-2">
            Options
          </button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "CardComponent",
  data() {
    return {
      rating: 4, // Default rating
      ratingStars:3
    };
  },
  computed: {
    ratingDescription() {
      if (this.rating === 5) return "Excellent";
      if (this.rating === 4) return "Very Good";
      if (this.rating === 3) return "Good";
      if (this.rating === 2) return "Fair";
      return "Poor";
    },
  },
  methods: {
    setRating(index) {
      this.rating = index;
    },
    setRatingStars(rate) {
      this.ratingStars = rate;
    },
  },
};
</script>

<style scoped>

</style>
