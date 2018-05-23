<template>
  <div id="TranslateOutput">
	<h2>{{translatedText}}</h2>
  </div>
</template>

<script>


export default {
  name: 'TranslateOutput',
  props:[
  	"translatedText"
  ]
}
</script>

<style>
	#TranslateOutput{
		color: lightgreen;font-size: 30px
	}
</style>
