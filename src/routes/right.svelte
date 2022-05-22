<script context="module">
	export const prerender = true;
</script>

<script lang="ts">
    import logo from './images/question.png';

	export let rightFirst:string;

    interface Person {
		name:string,
		status:string
	}
	let users:Person[] = [{name:'Вася',status:'empty'}, {name:'Петя',status:'empty'}, {name:'Коля',status:'empty'}];
	let name:string = '';
	let icon:string = logo;
	console.log(icon);
	function addUser(){
		users.push({name:name,status:'empty'});
		users = users;
		name = '';
	}
	function addUserKey(event:any){
		if (event.keyCode == 13){
			addUser();
		}
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
			{#each users as {name}}				
				<div class='list-user'><img src={logo} width="20px" alt="">{name}</div>
			{/each}
			<div class="add-user">
				<input type="text" bind:value={name} on:keydown={addUserKey}>
				<span class="add-user-but" on:click={addUser}>Добавить</span>
			</div>
		</div>
		<div class="friends tab-pane fade" id="friends">
			{#each users as {name}}				
				<div class='list-user'><img src={logo} width="20px" alt="">{name}</div>
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
</style>