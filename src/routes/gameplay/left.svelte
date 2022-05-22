<script context="module">
	export const prerender = true;
</script>

<script lang="ts">
    import mafia from '../images/mafia.jpg';
</script>

<div class="left-coloumn">  
    <div class="left-module">
        <div class="role">
            <div class="role-image"><img src={mafia} alt="изображение" height="200px"></div>
            <div class="role-name">Мафиози</div>
            <div class="role-description">Вы должны убить всех граждан</div>
        </div>
        <div class="mods">
            <div class="mods-header">
                Модификации игры
            </div>       
            <div class="mod">
                Игра без предметов
            </div>
            <div class="mod">
                Игра без приватного чата
            </div>
        </div>
    </div>
    <div class='bank'>

        <div class="bank-header">
            Банк игры
        </div>
        <div class="bank-gr">
            <div class="bank-name">
                Граждане
            </div>
            <div class="progress">
                <div class="progress-bar" role="progressbar" style="width: 33%;" aria-valuenow={33} aria-valuemin={0} aria-valuemax={100}>3300$</div>
            </div>
        </div>
        <div class="bank-mafia">
            <div class="bank-name">
                Мафиози 
            </div>
            <div class="progress">
                <div class="progress-bar" role="progressbar" style="width: 17%;" aria-valuenow={17} aria-valuemin={0} aria-valuemax={100}>1700$</div>
            </div>
        </div>
        <div class="bank-win">
            <div class="bank-name">
                Банк победы
            </div>
            <div class="progress">
                <div class="progress-bar" role="progressbar" style="width: 50%;" aria-valuenow={50} aria-valuemin={0} aria-valuemax={100}>5000$</div>
            </div>
        </div>
    </div>    
</div>

<style lang="scss">
      $color-red: rgb(143, 0, 0);
      
    .left-coloumn{
		height:100%;
        display: flex;	
        flex-direction: column;
        justify-content: space-between;	
        background-color: black;
        border-radius: 20px;      
	}
    .left-module{
        width:100%;
        overflow: auto;
        padding: 10px;  
    }
    .role{
        text-align: center;
        padding-bottom: 20px;
        border-bottom: 2px solid white;
    }
    .role-name{
        font-size: 20pt;
        color: #9b1b00;
        font-weight: 600;
    }
    .mods{
        border-bottom: 2px solid white;
        padding-bottom: 20px;
        padding-top: 10px;
    }
    .mods-header{
        text-align: center;
        font-weight: 600;
    }
    .mod{
        font-size: 10pt;
        padding:2px;
        font-style: italic;
    }
    .bank{
        margin:10px;
    }
    .bank-header{
        text-align: center;
        font-weight: 600;
    }
    .progress-bar{
        background-color:goldenrod;
        color:black;
        border-radius: 0px 5px 5px 0px;
    }
</style>