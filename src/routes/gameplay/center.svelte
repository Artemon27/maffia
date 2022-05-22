<script context="module">
	export const prerender = true;
</script>

<script lang="ts">
    import nik1 from '../images/nik1.gif';
	import nik2 from '../images/nik2.gif';
	import night from '../images/night.png';
</script>

<div class="center-chat">
    <div class="center-chat-frame">
		<div class="time-block">
			<div class="time">
				<span>НОЧЬ</span> 01:10
			</div>
		</div>
		<div class="tome msg">
			<b>Вася: Вероника,</b> Я знаю, что ты Мафиози
		</div>
		<div class="msg">
			<b>Вероника: Вася,</b> Нет, это не я
		</div>
		<div class="msg">
			<b>Петя2:</b> А я гражданин
		</div>
		<div class="msg">
			<b>Вася3:</b> я тоже
		</div>
		<div class="msg">
			<b>Коля:</b> вы не умеете играть
		</div>
		<div class="tome msg">
			<b>Петя: Вероника,</b> я тебе верю
		</div>
		<div class="msg">
			<b>Вероника: Петя,</b> Спасибо
		</div>
		<div class="msg">
			<b>Вероника: Петя,</b> Спасибо
		</div>
		<div class="msg">
			<b><img src={nik1} alt="">:<img src={nik2} alt=""></b>, как дела?
		</div>
		<div class="msg">
			<b><img src={nik2} alt="">:<img src={nik1} alt=""></b>, ок
		</div>
		<div class="msg sysmsg">
			Наступила 2 ночь. Честные граждане спят. Всем остальным пора действовать
		</div>
		<div class="msg sysmsg">
			Доктор выехал на вызов
		</div>
	</div>
    <div class="center-chat-input">
        <input class="chat-input" type="text" placeholder="Введите сообщение">
        <span class="chat-send">Отправить</span>
    </div>
</div>

<style>
    .center-chat{
		height:100%;
        display: flex;	
        flex-direction: column;
        justify-content: space-between;
		background-color: black;
		border-radius: 20px;
        margin: 0 10px;
	}
	.center-chat-frame{
		margin:10px;
	}
	.center-chat-input{
		margin:10px;
		height:30px;	
		display: flex;
		justify-content: space-between; 
	}
	.chat-input{
		width:80%;
		border: 1px solid white;
		border-radius: 10px;
		background-color: black;
		color: white;		
		padding: 5px 10px;
	}
	.chat-send{
		width:15%;
		text-align: center;
		background-color: goldenrod;
		border-radius: 10px;
		padding: 2px;
		color: black;
	}
	.tome{
		border: 1px dashed white;
		border-radius: 10px;
	}
	.msg{
		padding: 2px;
		display: flex;
		align-items: end;
	}
	.msg b{
		color:goldenrod;
		font-style: italic;
		display: flex;
		align-items: end;
		margin-right: 3px;
	}
	.sysmsg{
		font-weight: bold;
		color:#900000;
		font-style: italic;
		font-size: 13pt;
		
	}
	.time-block{
        font-size: 15pt;
        display: flex;
        justify-content: space-between;
		float: right;
		border: 3px solid #900000;
		margin: 0px 0px 5px 5px;
		border-radius: 15px;
		padding: 3px;
    }
    .time{
        text-align: center;
        border-radius: 10px;
        display: inline-block;
        color:#8453e9;
        font-family: verdana;
        line-height: 30px;
    }
    .time span{
        font-size:13pt;
    }
	@media (max-width:500px){
		.center-chat{
			margin:0px;
		}
	}
</style>