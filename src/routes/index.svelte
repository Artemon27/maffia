<script context="module" lang="ts">
	export const prerender = true;
	
</script>
  
  
<script lang="ts">	
	import Left from './leftmain.svelte';
	import Center from './center.svelte';
	import Right from './right.svelte';
	import Header from './header.svelte';	

	var rightFirst:string = 'В зале';
</script>

<svelte:head>
	<title>Home</title>
	<meta name="description" content="Svelte demo app" />
</svelte:head>

<Header />
	

<div class="main-container">
	<div class="main-slider-first child">
		<Left />
	</div>
	<div class="main-slider-second child">
		<Center />
	</div>
	<div class="main-slider-third child">				
		<Right {rightFirst} />
	</div>	
</div>	
<style>
.main-container{
	font-family: sans-serif;
	
	display: flex;
	
	
}
.child{
	scroll-snap-align: start;
}	
</style>
