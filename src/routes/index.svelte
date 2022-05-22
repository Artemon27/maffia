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
	
<section>
	<div class="main-container">
		<div class="main-slider-first">
			<Left />
		</div>
		<div class="main-slider-second">
			<Center />
		</div>
		<div class="main-slider-third">				
			<Right {rightFirst} />
		</div>	
	</div>	
</section>

<style>
	
	
	
	
	
	
</style>
