<script lang="ts">
	// This code fails in the browser with ERR_SVELTE_HYDRATION_MISMATCH
	import Log from './Log.svelte';
	let output: string[];
</script>

<Log bind:output />

<!-- On the top level, removing "Output:" and the #if block makes it work -->

<!-- Fails -->
Output: {#if output}{output}{/if}

<!-- Fails -->
{#if output}{output}{/if}

<!-- OK -->
Output: {output}

<!-- In an element, the #if block by itself works -->

<!-- Fails -->
<pre>
Output: {#if output}{output}{/if}
</pre>

<!-- OK -->
<pre>
{#if output}{output}{/if}
</pre>

<!-- OK -->
<pre>
Output: {output}
</pre>

<!-- Testing output.length works! -->

<!-- OK -->
Output: {#if output.length}{output}{/if}

<!-- OK -->
{#if output.length}{output}{/if}

<!-- OK -->
<pre>
Output: {#if output.length}{output}{/if}
</pre>

<!-- OK -->
<pre>
{#if output.length}{output}{/if}
</pre>

<!-- OK -->
<pre>
Output: {output}
</pre>
