<script lang="ts">
	import * as Tabs from '$lib/components/ui/tabs';
	import * as Card from '$lib/components/ui/card';
	import { Check } from 'lucide-svelte';
	import { Button } from '$lib/components/ui/button';

	type Plan = {
		type: 'free' | 'paid';
		name: string;
		price: number;
		description?: string;
		features: string[];
	};

	const freePlans: Plan[] = [
		{
			type: 'free',
			name: 'Free',
			price: 0,
			description: 'Ad-supported',
			features: [
				'Hosted on answeroverflow.com',
				'Index content into Google',
				'AI Question Answers',
				'Community Insights',
				'Host on your own domain'
			]
		}
	];

	const paidPlans: Plan[] = [
		{
			type: 'paid',
			name: 'Basic',
			price: 10,
			description: 'Ad-supported',
			features: [
				'Hosted on answeroverflow.com',
				'Index content into Google',
				'AI Question Answers',
				'Community Insights',
				'Host on your own domain'
			]
		},
		{
			type: 'paid',
			name: 'Pro',
			price: 20,
			description: 'Ad-supported',
			features: [
				'Hosted on answeroverflow.com',
				'Index content into Google',
				'AI Question Answers',
				'Community Insights',
				'Host on your own domain'
			]
		},
		{
			type: 'paid',
			name: 'Enterprise',
			price: 50,
			description: 'Ad-supported',
			features: [
				'Hosted on answeroverflow.com',
				'Index content into Google',
				'AI Question Answers',
				'Community Insights',
				'Host on your own domain'
			]
		}
	];
</script>

<section class="grid w-full grid-cols-1 items-center gap-8 px-8 py-16">
	<span class="text-center font-semibold uppercase tracking-wider text-muted-foreground">
		Pricing
	</span>
	<div class="flex flex-col items-center justify-start">
		<Tabs.Root value="free" class="flex w-full flex-col items-center gap-4">
			<Tabs.List class="mx-auto w-full max-w-md">
				<Tabs.Trigger value="free" class="w-full">Free</Tabs.Trigger>
				<Tabs.Trigger value="paid" class="w-full">Paid</Tabs.Trigger>
			</Tabs.List>
			<Tabs.Content value="free" class="w-full">
				<div class="flex w-full flex-row flex-wrap justify-center gap-8">
					{#each freePlans as plan}
						<Card.Root class="min-w-min max-w-lg grow">
							<Card.Header>
								<Card.Title class="text-2xl">${plan.price} / month</Card.Title>
								<Card.Description>{plan.description}</Card.Description>
							</Card.Header>
							<Card.Content>
								<ul role="list" class="flex flex-col items-start gap-2">
									{#each plan.features as feature}
										<li class="flex flex-row items-center gap-2">
											<Check class="size-4" />
											<span>
												{feature}
											</span>
										</li>
									{/each}
								</ul>
							</Card.Content>
							<Card.Footer>
								<Button class="w-full" variant="secondary">Get started</Button>
							</Card.Footer>
						</Card.Root>
					{/each}
				</div>
			</Tabs.Content>
			<Tabs.Content value="paid" class="w-full">
				<div class="flex w-full flex-row flex-wrap justify-center gap-8">
					{#each paidPlans as plan}
						<Card.Root class="min-w-min max-w-lg grow">
							<Card.Header>
								<Card.Title class="text-2xl">${plan.price} / month</Card.Title>
								<Card.Description>
									{plan.price !== 0 ? `or $${plan.price * 10} / year` : 'Contact us'}
								</Card.Description>
							</Card.Header>
							<Card.Content>
								<ul role="list" class="flex flex-col items-start gap-2">
									{#each plan.features as feature}
										<li class="flex flex-row items-center gap-2">
											<Check class="size-4" />
											<span>
												{feature}
											</span>
										</li>
									{/each}
								</ul>
							</Card.Content>
							<Card.Footer>
								<Button class="w-full" variant="secondary">Get started</Button>
							</Card.Footer>
						</Card.Root>
					{/each}
				</div>
			</Tabs.Content>
		</Tabs.Root>
	</div>
</section>
