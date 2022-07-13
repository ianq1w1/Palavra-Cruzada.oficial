<svelte:head>
	<link rel="stylesheet" href="/css/Jogostyle.css">
</svelte:head>

<script>

import {Contagem} from './Logica.js'
import VoltarMenu from './CVoltarMenu.svelte'
import { estado } from "./CEstado.js"
import { trocarEstadoDoJogo } from './CEstado.js'

function Preencher(){
 let letras = document.getElementById('resposta1')
    	if(letras == 1){
        	return 0 
    	}else{
        	tabelaVazia.push(letras) //alterar variável dentro do else á cada nova cruzada 
			console.log(letras)
    	}	
}


export let tabelaVazia = [ 
	[], //so coloque mais colchetes se tiver mais uma linha do array
	[],
	[],
	[],
	[],
	[],
	[],
	[]
]

export let tabelaResposta = [
	[1,1,"a","n","d","r","o","m","e","d","a",1,1,1],   //inserir letras, 1 a cada espaço vazio
	[1,1,1,"e","s","t","r","e","l","a","s",1,1,1],	// todas as letras da array devem ser minusculas e sem acentuação
	[1,1,1,"b","u","r","a","c","o","n","e","g","r","o"],
	[1,1, 1,"u",1,1,1,1,1,1,1,1,1,1],
	["v","i","a","l","a","c","t","e","a",1,1,1,1,1],  
	[1, 1, 1, "o",1,1,1,1,1,1,1,1,1,1],	
	[1, 1, 1, "s",1,1,1,1,1,1,1,1,1,1],
	[1 ,1,"g","a","l","a","x","i","a",1,1,1,1,1]	
] 


export let coluna = tabelaResposta[1].length + 1 //nas tabelas novas só precisa trocar o nome dessa variavel
console.log(coluna)
</script>
<!--modelo do jogo em html-->
<body>

<nav id="linha">
	<h2>
		Cruzada nível 1
	</h2>
</nav>

 

<section id="cruzada">
	
	<table>
		{#each Array(coluna) as _, row }
			<th>{row}</th>	
		{/each}
		{#each tabelaResposta as linha,i} <!--substituir a variável do each pela tabela resposta da nova cruzada-->
			<tr>
				 {i}
				 {#each linha as _tabelaResposta,j}	
					 {#if tabelaResposta[i][j] == 1}
						<td id="vazio">
							<img id="vazio" src="images\estrelinha.png" alt="estrela">
						</td>
					{:else}
						<td>
							<input maxlength="1" bind:value={tabelaVazia[i][j]} id="resposta1" > <!--alterar o bind:value pela array da tabela vazia da nova cruzada-->
						</td> <!--id de lógica, para estilizar crie outro--> <!--respostas do jogo tem q ser com caps desligado-->
					{/if}
				{/each} 
			</tr>
		{/each}
	</table>
	<button  class="enviar" on:click="{()=> Preencher()}" on:click="{()=> Contagem(tabelaVazia,tabelaResposta,5)}" >Enviar resposta</button>	
	<!--alterar parametros da function Contagem com : array vazia, array resposta e quantidade de letras válidas á cada nova cruzada-->
	<br>
</section>

<table id="dicas"> <!--tabela de dicas-->
	<tr id="dicas">
		L0. uma das galáxias mais próximas de nós
	</tr>
	<tr id="dicas">
		L1. as galáxias são formadas de bilhões de...
	</tr>
	<tr id="dicas">
		L2. objeto formado pela explosão de uma estrela,que engole até a luz
	</tr>
	<tr id="dicas">
		L4. nome da nossa galáxia
	</tr>
	<tr id="dicas">
		L7. o universo é formado por milhões de....
	</tr>
	<tr id="dicas">
		C4. nuvem de gás e poeira que dá origem às estrelas
	</tr>
	
	
</table>


	


	<VoltarMenu/>
	<div id="ajuda" class='menu' on:click="{() => trocarEstadoDoJogo('ajuda jogo1')}">
	ajuda
	</div>
	</body>