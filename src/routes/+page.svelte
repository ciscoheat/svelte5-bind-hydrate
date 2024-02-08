<script lang="ts">
	import Log from './Log.svelte';
	let output: (string[] | undefined)[];
</script>

<Log bind:output />

<!-- Removing "Output:" or the #if block makes it work -->
<pre>
Output: {#if output}{output}{/if}
</pre>

<pre>
{#if output}{output}{/if}
</pre>

<pre>
Output:
</pre>
