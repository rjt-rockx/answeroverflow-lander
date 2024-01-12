<script lang="ts">
	import { Button } from '$lib/components/ui/button';

	type FooterLink = {
		name: string;
		href: string;
	};

	type FooterSection = {
		name: string;
		links: FooterLink[];
	};

	const footerSections: FooterSection[] = [
		{
			name: 'Legal',
			links: [
				{
					name: 'Terms of Service',
					href: '/terms'
				},
				{
					name: 'Privacy Policy',
					href: '/privacy'
				},
				{
					name: 'Cookies',
					href: '/cookies'
				},
				{
					name: 'EULA',
					href: '/eula'
				}
			]
		},
		{
			name: 'Product',
			links: [
				{
					name: 'About',
					href: '/about'
				},
				{
					name: 'Docs',
					href: '/docs'
				},
				{
					name: 'Pricing',
					href: '/pricing'
				},
				{
					name: 'Contributors',
					href: '/contributors'
				},
				{
					name: 'Communities',
					href: '/communities'
				},
				{
					name: 'Changelog',
					href: '/changelog'
				}
			]
		}
	];
</script>

<footer class="flex w-full flex-col items-center justify-start gap-4">
	<div class="mx-auto flex w-full max-w-7xl flex-row flex-wrap items-start justify-start gap-8">
		{#each footerSections as footerSection}
			<div class="flex w-full min-w-min max-w-lg flex-col items-start justify-start gap-2">
				<span class="text-base font-semibold text-muted-foreground">
					{footerSection.name}
				</span>
				{#each footerSection.links as footerLink}
					<Button variant="link" class="h-fit p-0 text-base" href={footerLink.href}>
						{footerLink.name}
					</Button>
				{/each}
			</div>
		{/each}
	</div>
</footer>
