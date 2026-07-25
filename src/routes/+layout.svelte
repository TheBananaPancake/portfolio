<!--
SPDX-FileCopyrightText: 2026 TheBananaPancake <did:plc:3ywraszv5eqhnlvzumwju5fa>
SPDX-License-Identifier: MIT
-->

<script lang="ts">
	import favicon from '$lib/assets/favicon.svg';

	let { children } = $props();
</script>

<svelte:head>
	<link rel="icon" href={favicon} />
</svelte:head>

{@render children()}
