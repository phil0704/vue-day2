<template>
   <article class="accordion" :class="{ 'accordion-hide': hide }">
      <h2 @click="toggleHide()">
          {{ title }}
      </h2>
      <p>
         {{ content }}
      </p>
       </article> 
</template>

<script>
  export default {
      name: 'Accordion',
      props: [
          'title',
          'content'
      ],
      data () {
          return {
              hide: true
          }  
      },
      methods: {
          toggleHide () {
           // Convert boolean from true to false, or false to true.   
              this.hide = !this.hide;
          }
      }
  }
</script>

<style>
.accordion p {
    max-height: 100px;
    overflow: hidden;
    transition: 0.3s ease all;
}
  .accordion-hide p {
    max-height: 0;
  }
</style>