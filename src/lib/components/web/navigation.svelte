<script lang="ts">
	import { Button } from '$lib/components/ui/button';
	import { mode, toggleMode } from 'mode-watcher';
	import { Sun, Moon } from 'lucide-svelte';
</script>

<header class="sticky top-0 z-10 flex w-full flex-row bg-background p-4">
	<nav class="mx-auto flex max-w-7xl grow flex-row items-center justify-between gap-4">
		<Button variant="ghost">
			<span class="text-lg">Answer Overflow</span>
		</Button>
		<Button variant="ghost" size="icon" on:click={toggleMode}>
			{#if $mode === 'dark'}
				<Moon />
			{:else}
				<Sun />
			{/if}
		</Button>
	</nav>
</header>
