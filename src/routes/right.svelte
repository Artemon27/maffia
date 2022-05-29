<script context="module">
	export const prerender = true;

</script>

<script lang="ts">
    import logo from './images/question.png';
	import avka from './images/avka.jpg';
	import About from './about.svelte';
	import Center from './center.svelte';

	import {setNoContext} from './functions.svelte';
	import Contextuser from './contextuser.svelte';

	
	export let rightFirst:string;

    interface Person {
		id:number,
		name:string,
		status:string,
		image?:string
	}
	let users:Person[] = [{id:1, name:'Вася',status:'Здесь должен быть ваш статус',image:avka}, {id:2, name:'Петя',status:'empty'}, {id:3,name:'Коля',status:'empty'}];
	let name:string = '';
	let icon:string = logo;
	let userinfo:number = 0;
    let idContext:number = 0;

	console.log(icon);
	function addUser(){
		users.push({id:5,name:name,status:'empty'}); 
		users = users;
		name = '';
	}
	function addUserKey(event:any){
		if (event.keyCode == 13){
			addUser();
		}
	}
	function getuserinfo(id:number):any{
		if (userinfo != id){
			userinfo = id;
		}
	}
	function nulluserinfo(){
		userinfo = 0;
	}

</script>

<div class="right-coloumn">
	<div class="people-header nav nav-tabs">
		<button class="people-tab nav-link active" data-bs-toggle="tab" data-bs-target="#people" type="button" role="tab" aria-controls="home" aria-selected="true">{rightFirst}</button>
		<button class="friends-tab nav-link" data-bs-toggle="tab" data-bs-target="#friends" type="button" role="tab" aria-controls="home" aria-selected="true">Друзья</button>
		<button class="settings-tab nav-link" data-bs-toggle="tab" data-bs-target="#settings" type="button" role="tab" aria-controls="home" aria-selected="true">Настройки</button>
	</div>
	<div class ="right-content tab-content">
		<div class="people tab-pane fade show active" id="people">
			{#each users as {name,id,image,status}}
				<div class="userfullinfo">
					<div class="userinfo">
						<div class="userinfo-in">
							<div class="userinfo-name">
								{name}														
							</div>			
							{#if image!=undefined}
								<img class="avka" src={image} alt="">
							{:else}
								<div class="avka"></div>
							{/if}	
							<div class="userinfo-status">
								{status}														
							</div>
						</div>		
					</div>
					<Contextuser bind:idContext {id} idModule={10000}>
					<div slot="item" class='list-user'><img src={logo} width="20px" alt="">{name}</div>
					</Contextuser>
				</div>
			{/each}
			<div class="add-user">
				<input type="text" bind:value={name} on:keydown={addUserKey}>
				<span class="add-user-but" on:click={addUser}>Добавить</span>
			</div>
		</div>
		<div class="friends tab-pane fade" id="friends">
			{#each users as {name,id}}			
				<Contextuser bind:idContext {id} idModule={10001}>
					<div slot="item" class='list-user'><img src={logo} width="20px" alt="">{name}</div>
				</Contextuser>	
			{/each}
		</div>
		<div class="settings tab-pane fade" id="settings">

		</div>		
	</div>
</div>

<style>
    .right-coloumn{
		height: 100%;
		padding:10px;
		background-color: black;
		border-radius: 20px;
		overflow: auto;
	}
	.people-header{
        display: flex;
        justify-content: space-between;
	}
	.nav-link{
		--bs-nav-tabs-link-active-bg:black;
		--bs-nav-tabs-link-active-color: $color-red;
		color:white;
	}
    .list-user{
		margin:5px;
	}
	.list-user img{
		padding-right:5px;
	}
	.add-user{
		margin-top:50px;
		display: flex;
	}
	.add-user-but{		
		border:1px solid black;
		background-color: blue;
		color: white;
		cursor: pointer;
		padding:5px;
	}
	.userinfo{
		display: none;
		position: absolute;
		margin-left:-300px;
		background-color: black;
		width:300px;
		height:400px;		
		padding: 5px;
		border: 2px solid gold;
		border-radius: 20px;
	}
	.userinfo-in{
		border: 2px solid gold;
		border-radius: 20px;
		height: 100%;
		padding: 20px;
		text-align: center;
	}
	.userinfo-name{
		font-size: 16pt;
		font-weight: 600;
		margin-bottom: 10px;
	}
	.userinfo-status{
		font-size: 12pt;
		text-align: left;
		margin-top: 10px;
	}
	.userfullinfo:hover .userinfo{
		display: block;
	}
	.avka{
		width:150px;
		height: 180px;
	}
</style>