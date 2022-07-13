<svelte:head>
	<link rel="stylesheet" href="/css/aj1.css">
</svelte:head>

<script>
import Jogo1 from "./Jogo1.svelte";
import {trocarEstadoDoJogo} from './CEstado'
</script>
<body>
    <div id="respostas">
        <ul>1-andrômeda</ul>
        <ul>2- estrelas</ul>
        <ul>3- buraco negro</ul>
        <ul>4- via láctea</ul>
        <ul>5- galáxia</ul>
        <ul>6- nebulosa</ul>
        </div>
       
</body>
<div id="ajuda" class='menu' on:click="{() => trocarEstadoDoJogo('jogar cruzada 1')}">
	fechar
</div>
<Jogo1/>