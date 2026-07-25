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
    	<button onclick={() => (activePage = 'DEV')} disabled={activePage === 'DEV'}>Software development</button>
    	<button onclick={() => (activePage = 'CAD')} disabled={activePage === 'CAD'}>CAD projects</button>
    </div>

    {#if activePage === 'HOME'}
    	<h1>> @TheBananaPancake<span id="blink">▊</span></h1>
    	<div class="center">
    		<p>CAD engineering & low-level software development</p>
    		<a href="https://tangled.org/thebananapancake.tngl.sh" target="_blank" class="button">
    			Tangled
    		</a>
    		<a href="https://thebananapancake.tngl.sh/gearbox/@thebananapancake" target="_blank" class="button">
    		    Gearbox
    		</a>
    	</div> <br />

    	<div class="center">
    		<a href="https://tangled.org/thebananapancake.tngl.sh/portfolio" target="_blank" class="hollow-button">
    			See this website's git repository
    		</a>
    	</div>
    {:else if activePage === 'DEV'}
    	<h1>> Software</h1>
    	<h2>Tools</h2>
    	<div class="grid">
    		<a href="https://ziglang.org" target="_blank">
    			<div class="panel">
    				<img src="/zig-icon.png" alt="Zig icon" />
    				<div class="panel-text">
    					<h3>Zig</h3>
    					<p>A compiled low-level systems programming language.</p>
    				</div>
    			</div>
    		</a>
    		<a href="https://git-scm.com" target="_blank">
    			<div class="panel">
    				<img src="/git-icon.png" alt="Git icon" />
    				<div class="panel-text">
    					<h3>Git</h3>
    					<p>A commonly-used version control system.</p>
    				</div>
    			</div>
    		</a>
    	</div>
    {:else if activePage === 'CAD'}
    	<h1>> Computer Aided Design</h1>
    	<p>
    		I use <a href="https://www.freecad.org/" target="_blank">FreeCAD</a> for part design and
    		<a href="https://www.kicad.org/" target="_blank">KiCAD</a> for PCB/electrical work. For
            designing CPUs, I use a mixture of <a href="https://wikipedia.org/wiki/Verilog" target="_blank">Verilog</a>
            and <a href="https://hardcaml.org" target="_blank">HardCaml</a>, depending on the project.
    	</p>
    {/if}
</main>

<style>
	main {
		background-color: #111827;
		color: white;
		font-family:
			'Lucida Sans', 'Lucida Sans Regular', 'Lucida Grande', 'Lucida Sans Unicode', Geneva, Verdana,
			sans-serif;
		margin-left: 30%;
		margin-right: 30%;
		font-size: 16px;
		padding: 40px;
		border-radius: 12px;
	}

	:global(body) {
	    background-color: #1b273e;
	}

	a {
	    color: #349df9;
		text-decoration: none;
	}
	a.button {
    	background-color: #22c55e;
    	border-width: 0px;
    	border-radius: 4px;
    	cursor: pointer;
    	padding: 8px;
    	box-shadow: 0 4px 0 #147878;
    	color: black;
	}
	a.hollow-button {
	    color: white;
		border-width: 4px;
		border-color: #1b273e;
		padding: 6px;
		border-style: solid;
		border-radius: 8px;
	}

	button {
	    background-color: #22c55e;
    	border-width: 0px;
    	border-radius: 4px;
    	cursor: pointer;
    	padding: 8px;
    	box-shadow: 0 4px 0 #147878;
    	color: black;
        font-size: 16px;
	}
	button:disabled {
	    background-color: #1b273e;
        color: white;
        border-width: 4px;
        border-color: #147878;
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
		color: #22c55e;
	}
	.grid {
		display: grid;
		grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
		gap: 16px;
	}
	.panel {
		background-color: #1b273e;
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
