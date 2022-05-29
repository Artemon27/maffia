<script context="module">
	export const prerender = true;


</script>

<script lang="ts">

import {outClick} from './functions.svelte';
export let idContext:number;
export let id:number;
</script>
<slot name="item"></slot>
{#if idContext===id}
    <ul use:outClick={() => idContext = 0} class='context-menu'>
        <li>Посмотреть профиль</li>
        <li>Написать в приват</li>
        <li>Добавить в друзья</li>
        <li>Подарить подарок</li>
    </ul>
{/if}

<style>
    .context-menu{
		position: absolute;
		background-color: black;
		width:250px;
		border:2px solid var(--main-red-color);
		border-radius: 10px;
		padding:10px;
	}
	.context-menu li{
		list-style: none;
		font-size: 12pt;
		margin:5px;
		padding:0px;
	}
	.context-menu li:hover{
		color:var(--main-red-color);
		cursor: pointer;
		font-weight: 600;
	}
</style>