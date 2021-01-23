<template>
  <div id="app">
    <Navbar />
    <div class="container">
    	<router-view />
    </div>
  </div>
</template>

<style>

</style>


<script>
import Navbar from '@/components/Navbar.vue'
export default {
	components: {
		Navbar
	}
}
</script>