<template>
  <div class="testimonials py-5">
    <div class="container py-5">
      <h2 class="text-center py-3">Feedback</h2>
      <Carousel v-bind="settings" :breakpoints="breakpoints" :wrap-around="true">
        <Slide v-for="testimonial in testimonials" :key="slide" class="py-2">
          <div class="carousel__item">
            <div class="testimonial-card px-3 py-5 mx-3">
              <p class="fw-semibold">{{ testimonial.name }}</p>

              <p class="pt-4">{{ testimonial.content }}</p>
            </div>
          </div>
        </Slide>

        <template #addons>
          <Navigation />
        </template>
      </Carousel>

    </div>
  </div>
</template>

<script>
import { Carousel, Navigation, Slide } from 'vue3-carousel'
import { defineComponent } from 'vue'

export default defineComponent({
  name: 'Breakpoints',
  components: {
    Carousel,
    Slide,
    Navigation,
  },

  data() {
    return {
      // carousel settings
      settings: {
        itemsToShow: 1,
        snapAlign: 'center',
      },

      breakpoints: {
        // 700px and up
        900: {
          itemsToShow: 2,
          snapAlign: 'center',
        },
        // 1024 and up
        1024: {
          itemsToShow: 3,
          snapAlign: 'start',
        },
      },
      // images array
      testimonials:[
        { id: '1', name: 'Clara S', content: "Wow, that's all I can say. The pictures are perfect and more than expected. I recommend to everyone." },
        { id: '2', name: 'Patrick H', content: "We had a family photo shoot and we are very satisfied, my wife is impressed. The pictures were ready after 2 days. Thank you." },
        { id: '3', name: 'Ivan S', content: "At first I was embarrassed, but Faruk gave me some advice and in the end I completely relaxed and can't wait to go again. See you soon." },
        { id: '4', name: 'Day I', content: "I met Faruk last week, he is very kind and the pictures are fantastic, thank you very much and see you on another occasion." },
        { id: '5', name: 'Marija G', content: "Affordable prices and quality pictures. No more needed, thank you very much." },
        { id: '6', name: 'Chris J', content: "Beautiful photos and quality." }
      ]
    };
  },
});


</script>

<style setup>

.testimonials {
  background: #f3f3f3;
}
.testimonial-card {
  background: white;
  /* border-radius: 20px; */
  position: relative;
  height: 250px;
  
}

</style>