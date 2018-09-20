<template>
  <div id="translateOutput">
	  <ul class="list-unstyled">
		  <li v-for='text in arrayTranslate'><h4>{{text}}</h4></li>
	</ul>
<!--    <h5>{{arrayTranslate}}</h5>-->
  </div>
</template>

<script>

export default {
  name: 'arrayTranslate',
  props:['arrayTranslate']
}
</script>

<style>

</style>
