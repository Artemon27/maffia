<script context="module">
	export const prerender = true;


</script>

<script lang="ts">

import {outClick, setNoContext} from './functions.svelte';
export let idContext:number;    //Триггер включения/выключения меню
export let id:number;           //id пользователя
export let idModule:number;     //id модуля, в котором отображается меню

id = id * Math.pow(10, Math.floor(Math.log10(idModule)) + 1) + idModule;

export function userRightClick(e:MouseEvent, id:number){
    idContext = id;
    setNoContext();
}

</script>
<span on:contextmenu|preventDefault={(event)=>userRightClick(event,id)}>
<slot name="item"></slot>
</span>
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