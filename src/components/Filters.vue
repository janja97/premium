<template>
   <div>
    <div class="grid-div">
      <div class=""  v-for="image in images" :key="image.id" :class=" image.class ">
        <img  :src="image.UrlImg" alt="image.alt" >
      </div>
	  </div>
    <div class="d-flex col-10 text-de">
      Photography is a way of feeling, of touching, of loving. What you have caught on film is captured forever… It remembers little things, long after you have forgotten everything.
    </div>
    <div class="grid-div mt-0">
      <div class=""  v-for="img in images2" :key="img.id" :class=" img.class ">
        <img  :src="img.UrlImg" alt="img.alt" >
      </div>
	  </div>
    <div class="d-flex col-10 text-de">
      One of my favorite parts of my job is you: the people I get to meet and work with. It is such an honor to be asked to capture important moments in people’s lives.
    </div>
   </div>
</template>

<script>
import { ref } from '@vue/reactivity';

export default {
  name: 'AppFilters',
//   class: horizontal (2x1), vertical (1x2), none (2x2), big (4x4)
// type : natural-1 , peope-2 , clijent-3 , hotel-4 , street-5
data: () => ({
    images : [
      { id: '1' ,type: '2', UrlImg:'image1/people (4).jpeg' , alt:'image-slug', class:"vertical" },
      { id: '1' ,type: '2', UrlImg:'image1/people (6).jpeg' , alt:'image-slug', class:"big" },
      { id: '1' ,type: '2', UrlImg:'image1/people (8).jpeg' , alt:'image-slug', class:"vertical" },
      { id: '1' ,type: '2', UrlImg:'image1/people (1).jpeg' , alt:'image-slug', class:"vertical" },
      { id: '1' ,type: '2', UrlImg:'image1/people (9).jpeg' , alt:'image-slug', class:"vertical" },
      { id: '1' ,type: '2', UrlImg:'image1/people (13).jpeg' , alt:'image-slug', class:"vertical" },
      { id: '1' ,type: '2', UrlImg:'image1/people (7).jpeg' , alt:'image-slug', class:"vertical" },
      { id: '1' ,type: '2', UrlImg:'image1/people (5).jpeg' , alt:'image-slug', class:"vertical" },
      { id: '5', type: '2', UrlImg: 'home1/peope (5).jpeg', alt: 'image-slug', class: 'vertical' },
      { id: '1' ,type: '2', UrlImg:'image1/people (3).jpeg' , alt:'image-slug', class:"vertical" },
      { id: '1' ,type: '2', UrlImg:'image1/people (2).jpeg' , alt:'image-slug', class:"vertical" },
      { id: '1' ,type: '2', UrlImg:'image1/people (10).jpeg' , alt:'image-slug', class:"vertical" },
      { id: '1' ,type: '2', UrlImg:'image1/people (12).jpeg' , alt:'image-slug', class:"vertical" },
      { id: '1' ,type: '2', UrlImg:'image1/people (14).jpeg' , alt:'image-slug', class:"vertical" },
      { id: '2', type: '2', UrlImg: 'home1/people (3).jpeg', alt: 'image-slug', class: 'vertical' },
      { id: '3', type: '2', UrlImg: 'home1/peope (4).jpeg', alt: 'image-slug', class: 'vertical' },
       
    ],
    images2 : [
      { id: '1' ,type: '2', UrlImg:'image2/people (1).jpeg' , alt:'image-slug', class:"vertical" },
      { id: '1' ,type: '2', UrlImg:'image2/people (4).jpeg' , alt:'image-slug', class:"vertical" },
      { id: '1' ,type: '2', UrlImg:'image2/people (2).jpeg' , alt:'image-slug', class:"vertical" },
      { id: '1' ,type: '2', UrlImg:'image2/people (3).jpeg' , alt:'image-slug', class:"vertical" },
    ],
  }),
};
</script>

<style setup>
.nav a {
    color: black !important;
    margin: 0px 2px;
    font-size: 16px;
    font-weight: 600;
    letter-spacing: .5px;
    cursor: pointer;

}
.nav a:not(:last-child)::after {
    margin-left: 2px;
    content: "-";
}
.nav:last-child::after {
    display: none;
}
/* galery */

.grid-div> div {
    display: flex;
    justify-content: center;
    align-items: center;
    font-size: 2em;
    color: #ffeead;
}

.grid-div > div > img , image{
    width: 100%;
    height: 100%;
    object-fit: cover;
}

/* Grid */
.grid-div {
    margin-top: 80px;
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
    grid-auto-rows: 200px;
	grid-auto-flow: dense; /* Fill all spaces with fitted images */
}

.horizontal {
	grid-column: span 2;
}

.vertical {
	grid-row: span 2;
}

.big {
	grid-column: span 2;
	grid-row: span 2;
}
@media screen and (max-width: 460px) {
  .grid-div {
    display: block !important;
  }
  
}
.col-6 {
  display: flex;
  justify-content: center;
  align-items: center;
  font-size: 2em;
  color: #ffeead;
}
.text-de {
  font-size: 20px;
  align-items: center;
  justify-content: center;
  margin: 100px auto;
  text-align: center;
}
.vertical , .big {
  opacity: 0;
  transform: translateY(50px);
  animation: fadeInUp 1s ease-in-out forwards;
}

@keyframes fadeInUp {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}



</style>