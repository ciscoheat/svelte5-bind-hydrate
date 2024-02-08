<script lang="ts">
	import Log from './Log.svelte';
	let output: (string[] | undefined)[];
</script>

<Log bind:output />

<!-- Removing Output: makes it work -->
<pre>
Output: {#if output}{output.join('\n')}{/if}
</pre>
