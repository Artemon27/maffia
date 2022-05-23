    <script context="module" lang="ts">
	export const prerender = true;
    import { page } from '$app/stores';
    </script>
    <script lang="ts">
    let open:boolean = false;

	function outClick(node:Node, cb:Function) {
		if(window instanceof Window) {
			window.onclick = (e) => {
				if(e.composedPath().includes(node) || e.defaultPrevented) return
				cb()
			}
		}
		return { 
			destroy() {
				window.onclick = null
			}
		}
	}
    function openblock(){
        open = !open;
    }
</script>
<nav class="navbar navbar-expand-lg navbar-dark bg-black">
    <div class="container-fluid">
        <button on:click|preventDefault={openblock} class="navbar-toggler">
          <span class="navbar-toggler-icon"></span>
        </button>
        
        {#if open}
        <div use:outClick={() => open = !open} class="menu-mobile" id="">
            <ul class="header">
              <li class="nav-item">
                  <a class='nav-link' sveltekit:prefetch href="/gameset">Кнопка</a>
              </li>
              <li class="nav-item">
                  <a class='nav-link' sveltekit:prefetch href="/gameplay/gameplay">Кнопка</a>
              </li>
              <li class="nav-item">
                  <span class='nav-link'>Кнопка</span>
              </li>
              <li class="nav-item">
                  <span class='nav-link'>Кнопка</span>
              </li>
            </ul>
          </div>
        {/if}
        <div class="collapse navbar-collapse" id="navbarNav">
          <ul class="navbar-nav header">
            <li class="nav-item">
                <a class='nav-link' sveltekit:prefetch href="/gameset">Кнопка</a>
            </li>
            <li class="nav-item">
                <a class='nav-link' sveltekit:prefetch href="/gameplay/gameplay">Кнопка</a>
            </li>
            <li class="d-none d-lg-flex d-xl-flex d-xxl-flex main-info  ">
                <div class="info-name">
                    Вероника
                </div>
                 
                <div class="info-money">
                    Баланс: 45 000$
                    <span class="green-money">
                        50₤
                    </span>
                </div>
            </li>
            <li class="nav-item">
                <span class='nav-link'>Кнопка</span>
            </li>
            <li class="nav-item">
                <span class='nav-link'>Кнопка</span>
            </li>
          </ul>
        </div>
      </div>
    <div class="d-lg-none d-xl-none d-xxl-none main-info main-info-abs">
        <div class="info-name">
            Вероника
        </div>
         
        <div class="info-money">
            45 000$
            <span class="green-money">
                50₤
            </span>
        </div>
    </div>
</nav>

<style>
    .navbar{
        height: 50px;
        padding: 0px;
    }
    .menu-mobile{
        width: 250px;
        background-color: black;
        color: white;
        position: absolute;
        top: 50px;
        font-size: 18px;
        border-radius: 0px 0px 20px 20px;
    }
    .menu-mobile ul{
        flex-direction: column;
    }
    .menu-mobile li{
        padding:5px;
    }
    .menu-mobile li:hover{
        font-size: 19px;
        font-weight: 600;
    }
    a {
        text-decoration: none;

    }
    .main-info{
        display: flex;
        color:white;
        font-size: 15pt;
        line-height: 40px;
        justify-content: space-between;
        width:400px;
    }
    .main-info-abs{
        position: absolute;
        right: 20px;
        width:auto;
    }
    .info-name{
        margin-right: 20px;
        font-size: 17pt;
        font-weight: 600;
    }
    .info-money{
        margin-left: 5px;
        color:goldenrod;
    }
    .green-money{
        margin-left:20px;
        color:green;
    }
</style>