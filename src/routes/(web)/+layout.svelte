<script lang="ts">
	import Navigation from '$lib/components/web/navigation.svelte';
	import Footer from '$lib/components/web/footer.svelte';
</script>

<Navigation />
<main class="isolate z-0 mx-auto flex w-full max-w-7xl flex-col items-center">
	<slot />
</main>
<Footer />
