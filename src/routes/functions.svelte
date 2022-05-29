<script context="module" lang="ts">
	export const prerender = true;

    let noContext:number = 0;

    export function outClick(node:Node, cb:Function) {
		if(window instanceof Window) {
			window.onclick = (e) => {
				if(e.composedPath().includes(node) || e.defaultPrevented) return
				cb()
			}
		}
		return { 
			destroy() {
				if (noContext==1){
					noContext = 0;
				}	
				else{
				window.onclick = null
				}
			}
		}
	}

    export function setNoContext(){
        noContext = 1;
    }
    
</script>

<script lang="ts">



    

</script>