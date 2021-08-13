<template>
  <div id="top">
    <Nav></Nav> 
  </div>
  <router-view/>
</template>

<script lang="ts">
import { defineComponent } from 'vue'
import Nav from '@/components/Nav.vue'

export default defineComponent({
  components: {
    Nav,
  }
})
</script>


<style>

</style>
