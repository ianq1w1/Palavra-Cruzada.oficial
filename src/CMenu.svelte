<svelte:head>
	<link rel="stylesheet" href="/css/menu.css"> <!-- aqui tu põe o css do menu, do lado de styles/ põe o nome do arquivo, cria um novo(para o menu) se quiser-->
</svelte:head>

<script>
	import { estado } from './CEstado.js'
	import { trocarEstadoDoJogo } from './CEstado.js'
</script>

<body>
    <div class="container">
        <div class="gif">
            <figure>
                <img alt="polvo" src="./images/polvo clovis.gif" />
            </figure>
        </div>
        
            
              <div class="jogar">
            <img class="logo" alt="logo" src="https://i.ibb.co/v38G3dw/170a38d3-b938-4a01-9f52-eae6f7dd52bf.jpgs"/>
            <button on:click={()=> trocarEstadoDoJogo("jogar cruzada 1")}>
                Jogar - Nível 1
            </button>
            <button on:click={()=> trocarEstadoDoJogo("jogar cruzada 2")}>
                Jogar - Nível 2
            </button>
            <button on:click={()=> trocarEstadoDoJogo("sobre")}>
                Sobre
            </button>
        </div>
        <figure class="foguet">
            <img alt="foguet" src="./images/foguet.gif"/>
        </figure>
		
        
    </div>
</body>