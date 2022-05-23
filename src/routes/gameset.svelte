<script context="module" lang="ts">
	export const prerender = true;
</script>
  
  
<script lang="ts">	
	import Leftset from './leftset.svelte';
	import Center from './center.svelte';
	import Right from './right.svelte';
	import Header from './header.svelte';

    var rightFirst:string = 'В наборе';
</script>

<Header />

<div class="main-container">
    <div class="main-slider-first">
        <Leftset />
    </div>
    <div class="main-slider-second">
        <Center />
    </div>
    <div class="main-slider-third">				
        <Right {rightFirst} />
    </div>	
</div>	