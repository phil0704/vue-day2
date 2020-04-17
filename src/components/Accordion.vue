<template>
   <article class="accordion" :class="{ 'accordion-hide': hide }">
      <h2>My Accordion</h2>
      <p>
          I'm text that will hide and show! 
          Click the title to toggle my visibility. :)
      </p>
       </article> 
</template>

<script>
  export default {
      name: 'Accordion',
      data () {
          return {
              hide: true
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