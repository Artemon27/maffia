<script context="module">
	export const prerender = true;
    import { page } from '$app/stores';
</script>

<script lang="ts">
    export let creator:string;
    export let type:string;
    export let money:number;
    export let peopleAll:number;
    export let peopleNow:number;
</script>


<a class="game-block-href" sveltekit:prefetch href="/gameset">
    <div class="game-block">
        <div class="game-creator">{creator}</div>
        <div class="game-type">{type}</div>
        <div class="game-money">{money}$</div>
        <div class="game-all">{peopleAll}</div>
        <div class="game-now">{peopleNow}</div>
    </div>
</a>

<style>
.game-block-href{
    text-decoration: none;
    color:white;
}
.game-block{
    width:100%;
    height:50px;
    background-color: rgba(255,255,255, 0.2);
    border-radius: 10px;
    margin-bottom: 10px;
    font-size: 11pt;
    text-align: center;   
    display: table;
}
.game-creator, .game-type, .game-money, .game-all, .game-now{
    height: 100%;
    display: table-cell;
    vertical-align: middle;
}
.game-creator{
    width:130px;     
    border-right: 1px solid white;
}
.game-type{
    width:90px;
    border-right: 1px solid white;
}
.game-money{
    width:50px;
    border-right: 1px solid white;
}
.game-all{
    width:30px;
    border-right: 1px solid white;
}
.game-now{
    width:30px;
}
</style>