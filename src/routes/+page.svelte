<!--
SPDX-FileCopyrightText: 2026 TheBananaPancake <did:plc:3ywraszv5eqhnlvzumwju5fa>
SPDX-License-Identifier: MIT
-->

<script lang="ts">
	let activePage = $state('HOME');
</script>


<svelte:head>
	<title>{`Banana Pancake // ${activePage}`}</title>
</svelte:head>

<main>
    <div class="center">
    	<button onclick={() => (activePage = 'HOME')} disabled={activePage === 'HOME'}>Home</button>
    	<button onclick={() => (activePage = 'SOFTWARE')} disabled={activePage === 'SOFTWARE'}>Software</button>
    	<button onclick={() => (activePage = 'HARDWARE')} disabled={activePage === 'HARDWARE'}>Hardware</button>
    </div>

    {#if activePage === 'HOME'}
        <h1>> Banana Pancake<span id="blink">▊</span></h1>
    	<div class="center">
    		<p>CAD engineering & systems development</p>
    		<a href="https://tangled.org/thebananapancake.tngl.sh" target="_blank" class="button">
    			Tangled
    		</a>
    		<a href="https://thebananapancake.tngl.sh/gearbox/@thebananapancake" target="_blank" class="button">
    		    Gearbox
    		</a>
    	</div> <br />
        <hr class="dashed" /> <br />
    	<div class="center">
    		<a href="https://tangled.org/thebananapancake.tngl.sh/portfolio" class="hollow-button">
    			See this website's git repository
    		</a>
    	</div>
    {:else if activePage === 'SOFTWARE'}
    	<h1>> Software</h1>
    	<h2>Tools</h2>
    	<div class="grid">
    		<a href="https://rust-lang.org" target="_blank">
    			<div class="panel">
    				<img src="/rustacean-icon.svg" alt="Rust mascot, Ferris the crab" />
    				<div class="panel-text">
    					<h3>Rust</h3>
    					<p>Memory-safe compiled systems programming language.</p>
    				</div>
    			</div>
    		</a>
    		<a href="https://git-scm.com" target="_blank">
    			<div class="panel">
    				<img src="/git-icon.png" alt="Git icon" />
    				<div class="panel-text">
    					<h3>Git</h3>
    					<p>Version control system.</p>
    				</div>
    			</div>
    		</a>
    	</div>
    {:else if activePage === 'HARDWARE'}
    	<h1>> Computer Aided Design</h1>
    	<p>
            For designing CPUs, I use a mixture of <a href="https://wikipedia.org/wiki/Verilog" target="_blank">Verilog</a>
            and <a href="https://hardcaml.org" target="_blank">HardCaml</a>.
    		I use <a href="https://www.freecad.org/" target="_blank">FreeCAD</a> for part design and
    		<a href="https://www.kicad.org/" target="_blank">KiCAD</a> for PCB/electrical work. See some of my projects below...
    	</p>
    {/if}
</main>

<style>
	main {
		background-color: #1e1e2e;
		color: white;
		font-family:
			'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana,
			sans-serif;
		margin-left: 25%;
		margin-right: 25%;
		font-size: 16px;
		padding: 40px;
		border-radius: 12px;
	}

	:global(body) {
	    background-color: #11111b;
	}

	a {
	    color: #1592ff;
		text-decoration: none;
	}
	a.button {
    	background-color: #31aae4;
    	border-width: 0px;
    	border-radius: 4px;
    	cursor: pointer;
    	padding: 8px;
    	box-shadow: 0 4px 0 #4641d9;
    	color: black;
	}
	a.hollow-button {
	    color: white;
		border-width: 4px;
		border-color: #323443;
		padding: 6px;
		border-style: solid;
		border-radius: 8px;
	}

	button {
	    background-color: #31aae4;
    	border-width: 0px;
    	border-radius: 4px;
    	cursor: pointer;
    	padding: 8px;
    	box-shadow: 0 4px 0 #4641d9;
    	color: black;
        font-size: 16px;
	}
	button:disabled {
	    background-color: #111827;
        color: white;
        border-width: 4px;
        border-color: #4641d9;
        padding: 6px;
        border-style: solid;
        border-radius: 8px;
        cursor: default;
        box-shadow: 0 0 0;
	}

	h1 {
		font-family: monospace;
		font-size: 48px;
		text-align: center;
	}

	hr.dashed {
	    color: #323443;
		border-top: 3px dashed #323443;
	}

	/*
	textarea {
		background-color: #1e1e2e;
		color: white;
		border-width: 0px;
		border-radius: 8px;
		font-family: monospace;
		font-size: 16px;
	}
	input {
		background-color: #1e1e2e;
		color: white;
		border-width: 0px;
		border-radius: 3px;
		font-family: monospace;
		font-size: 16px;
	}
	*/

	.center {
		text-align: center;
	}

	@keyframes blink {
		0%,
		50% {
			opacity: 0;
		}
		50%,
		100% {
			opacity: 1;
		}
	}
	#blink {
		animation: blink 1s infinite;
		animation-timing-function: steps(1);
		color: #4641d9;
	}
	.grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
		gap: 16px;
	}
	.panel {
		background-color: #11111b;
		border-radius: 8px;
		padding: 16px;
		display: flex;
		gap: 16px;
		align-items: flex-start;
	}

	.panel img {
		width: 100px;
		height: 100px;
		flex-shrink: 0;
	}

	.panel-text {
		display: flex;
		flex-direction: column;
	}

	a .panel {
		color: white;
	}
</style>
