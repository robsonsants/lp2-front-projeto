<template>
  <div class="slider container-fluid" style="margin:0;padding:0!important">
    <div :id="'slider' + item.id" class="carousel slide carousel-fade" data-ride="carousel">

      <ol class="carousel-indicators">
        <li :data-target="'#slider' + item.id" 
            v-for="(img, id) in item.imagesUrl" 
            :data-slide-to="id" 
            :class="[id==0 ? 'active' : '']"
            :key="'slider'+id">
        </li>
      </ol>

      <div class="carousel-inner">
        <div :class="['carousel-item', id==0 ? 'active' : '']" 
              v-for="(img, id) in item.imagesUrl" 
              :key="id">
          <img class="d-block w-100" 
              :class="{'border-img-slide':radius}"
              :src="img" 
              alt="1">
        </div>
      </div>

      <a class="carousel-control-prev" :href="'#slider' + item.id" role="button" data-slide="prev">
        <span class="carousel-control-prev-icon" aria-hidden="true"></span>
        <span class="sr-only">Previous</span>
      </a>
      <a class="carousel-control-next" :href="'#slider' + item.id" role="button" data-slide="next">
        <span class="carousel-control-next-icon" aria-hidden="true"></span>
        <span class="sr-only">Next</span>
      </a>
    </div>
  </div> <!-- div class -->
</template>

<script>
  export default {
    props: {
      item: Object,
      radius: Boolean
    },
  }
</script>

<style>
.border-img-slide {
  border-radius: 5px
}
</style>