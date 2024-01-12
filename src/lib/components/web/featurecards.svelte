<script lang="ts">
	import * as Card from '$lib/components/ui/card';

	type FeatureCard = {
		title: string;
		description: string;
	};

	export let features: FeatureCard[] = [
		{
			title: 'Index content into Google',
			description: 'Organically gain more users by ranking at the top of Google search results'
		},
		{
			title: 'AI Question Answers',
			description:
				'Automate answering common questions with AI answers sourced from your community content'
		},
		{
			title: 'Community Insights',
			description:
				'Understand your community better with analytics on what your users are searching for'
		},
		{
			title: 'Host on your own domain',
			description: "Boost your brand by hosting your community's content on your own domain"
		}
	];
</script>

{#each features as feature}
	<Card.Root>
		<Card.Header>
			<Card.Title>
				<span>{feature.title}</span>
			</Card.Title>
		</Card.Header>
		<Card.Content>
			<p class="text-muted-foreground">
				{feature.description}
			</p>
		</Card.Content>
	</Card.Root>
{/each}
