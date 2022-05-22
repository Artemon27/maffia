<script context="module" lang="ts">
	export const prerender = true;
</script>
  
  
<script lang="ts">	
	import Left from './left.svelte';
	import Center from './center.svelte';
	import Right from './right.svelte';
	import Header from '../header.svelte';

    var rightFirst:string = 'В игре';
</script>

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
    .child{
        scroll-snap-align: start;
    }	
    </style>