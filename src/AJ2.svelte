<svelte:head>
	<link rel="stylesheet" href="/css/aj1.css">
</svelte:head>

<script>
import Jogo2 from "./Jogo2.svelte";
import {trocarEstadoDoJogo} from './CEstado'
</script>
<body>
    <div id="respostas">
        <ul>1-marte</ul>
        <ul>2- eclipse</ul>
        <ul>3- venus</ul>
        <ul>4- urano</ul>
        <ul>5- meteoro</ul>
        </div>
       
</body>
<div id="ajuda" class='menu' on:click="{() => trocarEstadoDoJogo('jogar cruzada 2')}">
	fechar
</div>
<Jogo2/>