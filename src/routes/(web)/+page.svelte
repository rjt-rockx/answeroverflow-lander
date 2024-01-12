<script lang="ts">
	import { Button } from '$lib/components/ui/button';
	import FeatureCards from '$lib/components/web/featurecards.svelte';
	import Pricing from '$lib/components/web/pricing.svelte';
	import { cn } from '$lib/utils';

	import { Search } from 'lucide-svelte';
</script>

<section class="flex flex-col items-center justify-center gap-8 px-8 py-16 text-center">
	<h1 class="max-w-4xl text-balance text-4xl font-extrabold leading-normal lg:text-5xl">
		Make your community accessible to the web.
	</h1>
	<p class="max-w-prose text-pretty text-xl text-muted-foreground">
		Answer Overflow indexes your Discord server and publishes it online in a searchable, accessible
		format.
	</p>

	<div
		class="grid h-16 w-full max-w-2xl grid-cols-1 grid-rows-1 rounded-md border border-input bg-secondary text-base ring-offset-background has-[input:focus]:outline-none has-[input:focus]:ring-2 has-[input:focus]:ring-ring has-[input:focus]:ring-offset-2"
	>
		<input
			type="text"
			name="hero-search"
			id="hero-search"
			placeholder="Search hundreds of servers"
			class={cn(
				'h-16 w-full bg-transparent pl-4 pr-16 text-base leading-[3rem] text-secondary-foreground placeholder:text-muted-foreground focus:outline-none focus:ring-0 disabled:cursor-not-allowed disabled:opacity-50'
			)}
		/>
		<div class="flex h-16 w-16 flex-col items-center justify-center place-self-end">
			<Button variant="ghost" disabled size="icon" aria-label="Search">
				<Search class="size-4" />
			</Button>
		</div>
	</div>
	<div class="flex flex-row gap-4">
		<Button>Add your server</Button>
		<Button variant="secondary">Read the docs</Button>
	</div>
</section>
<section class="grid grid-cols-1 gap-8 px-8 py-16 md:grid-cols-2">
	<span
		class="col-span-full text-center font-semibold uppercase tracking-wider text-muted-foreground"
	>
		Features
	</span>
	<FeatureCards />
</section>
<Pricing />
