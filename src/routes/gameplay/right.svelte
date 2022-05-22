<script context="module">
	export const prerender = true;
</script>

<script lang="ts">
    import logo from '../images/question.png';
    import bug from '../images/bug.png';
    import car from '../images/car.png';
    import rac from '../images/rac.png';
    import mask from '../images/mask.png';
    import cart from '../images/cart.png';

	export let rightFirst:string;

    interface Person {
		name:string,
		status:string,
        role?:string
	}
	let users:Person[] = [{name:'Вася',status:'empty'}, {name:'Петя',status:'empty'}, {name:'Коля',status:'empty'},
    {name:'Вася2',status:'empty'}, {name:'Петя2',status:'empty'}, {name:'Коля2',status:'empty'},
    {name:'Вася3',status:'empty'}, {name:'Петя3',status:'empty'}, {name:'Коля3',status:'empty'},
    {name:'Вероника',status:'empty',role:'Мафиози'}, {name:'Света',status:'empty'}, {name:'Оля',status:'empty'}];
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

<div class="right-main">
    <div class="right-coloumn">
        <div class="people-header nav nav-tabs">
            <button class="people-tab nav-link active" data-bs-toggle="tab" data-bs-target="#people" type="button" role="tab" aria-controls="home" aria-selected="true">{rightFirst}</button>
            <button class="friends-tab nav-link" data-bs-toggle="tab" data-bs-target="#friends" type="button" role="tab" aria-controls="home" aria-selected="true">Друзья</button>
            <button class="settings-tab nav-link" data-bs-toggle="tab" data-bs-target="#settings" type="button" role="tab" aria-controls="home" aria-selected="true">Настройки</button>
        </div>
        <div class ="right-content tab-content">
            <div class="people tab-pane fade show active" id="people">
                {#each users as {name, role}}				
                    {#if role!=undefined}
                        <div class='list-user you'><img src={logo} width="20px" alt="">{name} - {role}</div>
                    {:else}
                        <div class='list-user'><img src={logo} width="20px" alt="">{name}</div>
                    {/if}
                {/each}
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
    <div class="right-bottom">
        <div class="action">
            <button>Убить</button>
        </div>
        <div class="store">
            <div class="store-item">
                <img height="60px" width="60px" src={rac} alt="">
                <button>
                    <img class="cart" width="40px" src={cart} alt="">
                </button>
            </div>  
            <div class="store-item">
                <img height="60px" width="60px" src={bug} alt="">
                <button>
                    <img class="cart" width="40px" src={cart} alt="">
                </button>
            </div>
            <div class="store-item">
                <img height="60px" width="60px" src={mask} alt="">
                <button>
                    <img class="cart" width="40px" src={cart} alt="">
                </button>
            </div>
            <div class="store-item">
                <img height="60px" width="60px" src={car} alt="">
                <button>
                    <img class="cart" width="40px" src={cart} alt="">
                </button>
            </div>
        </div>
    </div>
</div>

<style>
    .right-main{
        height: 100%;
		padding:10px;
		background-color: black;
		border-radius: 20px;
        display: flex;
        flex-direction: column;
        justify-content: space-between;
    }
    .right-coloumn{
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
    .you{
        font-weight: 600;
    }
	.list-user img{
		padding-right:5px;
	}
    .action{
        text-align: center;
    }
    .action button{
        width:70%;
        height: 40px;
        background-color: rgb(143, 0, 0);
        color:white;
        border-radius: 15px;
        border:none;
    }
    .store{
        margin-top: 20px;
        display: flex;
        justify-content: space-between;
    }
    .store-item{
        display: flex;
        flex-direction: column;
    }
    .store-item img{
        color:red;
        background-color: #900000;
    }
    .store-item .cart{
        background-color: unset;
        margin-top: -13px;
    }
    .store-item button{
        margin: auto;
        background-color: goldenrod;
        border-radius: 15px;
        border-color: gold;
        width:50px;
        cursor: pointer;
        margin-top: 5px;
        height: 20px;
    }
</style>