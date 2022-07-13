<svelte:head>
	<link rel="stylesheet" href="/css/Jogostyle.css">
</svelte:head>

<script>

import {Contagem} from './Logica.js'
import VoltarMenu from './CVoltarMenu.svelte'
import { estado } from "./CEstado.js"
import { trocarEstadoDoJogo } from './CEstado.js'

function Preencher(){
 let letras = document.getElementById('resposta2')
    	if(letras == 1){
        	return 0 
    	}else{
        	tabelaV2.push(letras) //alterar variável dentro do else á cada nova cruzada 
			console.log(letras)
    	}	
}


export let tabelaV2 = [ 
	[], //so coloque mais colchetes se tiver mais uma linha do array
	[],
	[],
	[],
	[],
	[],
	[],
	[]
]

export let tabelaR2 = [
	[1,1,1,1,"m","a","r","t","e",1,1],   //inserir letras, 1 a cada espaço vazio
	[1,1,1,1,"e","c","l","i","p","s","e"],	// todas as letras da array devem ser minusculas e sem acentuação
	[1,1,1,1,"t",1,1,1,1,1,1],
	[1,1,1,"v","e","n","u","s",1,1,1],
	["u","r","a","n","o",1,1,1,1,1,1],  
	[1,1,1,1,"r",1,1,1,1,1,1],	
	[1,1,1,1,"o",1,1,1,1,1,1],
	[1,1,1,1,"s",1,1,1,1,1,1]	
] 


export let coluna = tabelaR2[1].length + 1 //nas tabelas novas só precisa trocar o nome dessa variavel
console.log(coluna)
</script>
<!--modelo do jogo em html-->
<body>

<nav id="linha">
	<h2>
		Cruzada nível 2
	</h2>
</nav>

 

<section id="cruzada">
	
	<table>
		{#each Array(coluna) as _, row }
			<th>{row}</th>	
		{/each}
		{#each tabelaR2 as linha,i} <!--substituir a variável do each pela tabela resposta da nova cruzada-->
			<tr>
				 {i}
				 {#each linha as _tabelaR2,j}	
					 {#if tabelaR2[i][j] == 1}
						<td id="vazio">
							<img id="vazio" src="images\estrelinha.png" alt="estrela">
						</td>
					{:else}
						<td>
							<input maxlength="1" bind:value={tabelaV2[i][j]} id="resposta2" > <!--alterar o bind:value pela array da tabela vazia da nova cruzada-->
						</td> <!--id de lógica, para estilizar crie outro--> <!--respostas do jogo tem q ser com caps desligado-->
					{/if}
				{/each} 
			</tr>
		{/each}
	</table>
	<button  class="enviar" on:click="{()=> Preencher()}" on:click="{()=> Contagem(tabelaV2,tabelaR2,26)}" >Enviar resposta</button>	
	<!--alterar parametros da function Contagem com : array vazia, array resposta e quantidade de letras válidas á cada nova cruzada-->
	<br>
</section>

<table id="dicas"> <!--tabela de dicas-->
	<tr id="dicas">
		L0. planeta conhecido como planeta vermelho
	</tr>
	<tr id="dicas">
		L1. é um fenômeno onde um astro deixa de ser visível total ou parcialmente durante um período limitado
	</tr>
	<tr id="dicas">
		L3. planeta conhecido como Estrela Dalva
	</tr>
	<tr id="dicas">
		L4. planeta mais gelado do Sistema solar
	</tr>
	<tr id="dicas">
		C4. popularmente conhecido como Estrela cadente
	</tr>
	
	
</table>


	


	<VoltarMenu/>
	<div id="ajuda" class='menu' on:click="{() => trocarEstadoDoJogo('ajuda jogo2')}">
	ajuda
	</div>
	</body>