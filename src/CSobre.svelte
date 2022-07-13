<svelte:head>
	<link rel="stylesheet" href="/css/sobre.css">
</svelte:head>

<script>
	import VoltarMenu from './CVoltarMenu.svelte'
</script>
<body>
	
		<p class="cabeçalho">GRUPO DO PROJETO DO 1º PERÍODO DE TSI</p>
<table>
	<tr>
		<th>
<p>
		Marilia Feitosa - Github: <a href="https://github.com/marimoon">marimoon</a>
</p>
</th>
</tr>

<tr>
	<th>
<p>
	Ian Elton -  Github: <a href="https://github.com/ianq1w1">ianq1w1</a>
</p>
</th>
</tr>

<tr>
	<th>
<p>
	Isabela da Silva-  Github: <a href="https://github.com/belinha18">belinha18</a>
</p>
</th>
</tr>
<tr>
	<th>
<p>
	Cecilia -  Github: <a href="https://github.com/CeciliaCarol">CeciliaCarol</a>
</p></th>
</tr>
<tr>
	<th>
<p>
	Emerson lima  -  Github: <a href="https://github.com/EmersonLima03">EmersonLima03</a>
</p>
</th>
</tr>
</table>


<figure class="if
">
	<img alt="if" src="./images/if.gif"/>
</figure>



<VoltarMenu/>
<div id="ajuda" class='menu' on:click="{() => trocarEstadoDoJogo('ajuda jogo1')}">
	ajuda
	</div>
</body>