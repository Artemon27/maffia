<script context="module">
	export const prerender = true;
</script>

<script lang="ts">
    import Gameinfo from './gameinfo.svelte'
    interface Game {
		creator:string,
		type:string,
        money:number,
        peopleAll:number,
        peopleNow:number,
	};
	let games:Game[] = [
        {creator:'Вася',type:'Закрытая игра',money:8000,peopleAll:16,peopleNow:10}, 
        {creator:'Петя',type:'Игра с ботами',money:1000,peopleAll:8,peopleNow:5},
        {creator:'Коля весельчак',type:'Игра без ботов',money:2000,peopleAll:15,peopleNow:7}
    ];
</script>

<div class="left-coloumn">    
    <div class="left-games">
        <div class="games-header nav nav-tabs">
            <button class="classic nav-link active" id="home-tab" data-bs-toggle="tab" data-bs-target="#classic" type="button" role="tab" aria-controls="home" aria-selected="true">Классика</button>
            <button class="wall nav-link" id="home-tab" data-bs-toggle="tab" data-bs-target="#wall" type="button" role="tab" aria-controls="home" aria-selected="true">Стенки</button>
            <button class="ingame nav-link" id="home-tab" data-bs-toggle="tab" data-bs-target="#now-play" type="button" role="tab" aria-controls="home" aria-selected="true">Текущие</button>
        </div>
        <div class ="game-info tab-content">
            <div class="classic tab-pane fade show active" id="classic">
                {#each games as game}		
                    <Gameinfo {...game}/>		                
                {/each}   
                {#each games as game}		
                    <Gameinfo {...game}/>		                
                {/each}    
                {#each games as game}		
                    <Gameinfo {...game}/>		                
                {/each}    
                {#each games as game}		
                    <Gameinfo {...game}/>		                
                {/each}             
            </div>
            <div class="wall tab-pane fade" id="wall">

            </div>
            <div class="now-play tab-pane fade" id="now-play">
                {#each games as game}		
                    <Gameinfo {...game}/>		                
                {/each}            
            </div>
        </div>
    </div>
    <div class="create-game">
        <button class="create-game-btn">Создать партию</button>
    </div>
    
</div>

<style lang="scss">
      $color-red: rgb(143, 0, 0);
      
      .nav-link{
        --bs-nav-tabs-link-active-bg:black;
        --bs-nav-tabs-link-active-color: $color-red;
        color:white;
      }
    .left-coloumn{
		height:100%;
        display: flex;	
        flex-direction: column;
        justify-content: space-between;	
        background-color: black;
        border-radius: 20px;      
	}
	.left-games{	
		width:100%;
        overflow: auto;
        padding: 10px;  
	}    
    .games-header{
        display: flex;
        justify-content: space-between;
    }
    .game-info{
        margin-top: 10px;
    }
    .create-game{
        text-align: center;
        margin: 10px;
    }
    .create-game-btn{
        height: 40px;
        width:200px;
        padding:5px;
        background-color: $color-red;
        color:white;
        border: none;
        border-radius: 20px;
    }
</style>