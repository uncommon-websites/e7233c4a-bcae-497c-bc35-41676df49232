<!--
@component Pricing

Please update features according to the company's product offering. Do not remove this comment.
-->
<script lang="ts">
	// Types
	type PricingTier = {
		name: string;
		monthlyPrice?: number | null;
		yearlyPrice?: number | null;
		description: string;
		features: string[];
		cta: {
			label: string;
			href: string;
		};
		highlight?: boolean;
	};

	type PricingFeature = {
		name: string;
		tiers: {
			[key: string]: boolean | string;
		};
	};

	// Components
	import Button from "$lib/components/ui/Button.svelte";
	import SectionHeader from "./SectionHeader.svelte";
	import IconCheck from "~icons/lucide/check";
	import IconX from "~icons/lucide/x";
	import NumberFlow from "@number-flow/svelte";
	import LogoScroller from "./LogoScroller.svelte";

	// Props
	const {
		title = "Simple, human pricing",
		subtitle = "Support for individuals, teams, and leaders",
		tierNames = ["1:1 Coaching", "Team Development", "Retreats & Offsites"],
		features = [
		{
			name: "Sessions included",
			tiers: {
				"1:1 Coaching": "4–6 (80 min)",
				"Team Development": "6–12 (90–120 min)",
				"Retreats & Offsites": "1–5+ facilitated sessions"
			}
		},
		{
			name: "Program length",
			tiers: {
				"1:1 Coaching": "1–3 months",
				"Team Development": "3–6 months",
				"Retreats & Offsites": "1–3 days"
			}
		},
		{
			name: "Format",
			tiers: {
				"1:1 Coaching": "Zoom or in person",
				"Team Development": "Zoom, in person, or hybrid",
				"Retreats & Offsites": "In person only"
			}
		},
		{
			name: "Pre-program alignment",
			tiers: {
				"1:1 Coaching": "Chemistry call",
				"Team Development": "Team alignment call",
				"Retreats & Offsites": "2–3 planning sessions"
			}
		},
		{
			name: "Custom agenda / program",
			tiers: {
				"1:1 Coaching": false,
				"Team Development": true,
				"Retreats & Offsites": true
			}
		},
		{
			name: "Facilitation / hosting",
			tiers: {
				"1:1 Coaching": "1:1 coaching",
				"Team Development": "Team+exec facilitation",
				"Retreats & Offsites": "Onsite facilitation"
			}
		},
		{
			name: "Individual support",
			tiers: {
				"1:1 Coaching": true,
				"Team Development": "Optional add-on",
				"Retreats & Offsites": false
			}
		},
		{
			name: "Group support",
			tiers: {
				"1:1 Coaching": false,
				"Team Development": true,
				"Retreats & Offsites": true
			}
		},
		{
			name: "Recommended group size",
			tiers: {
				"1:1 Coaching": "1 person",
				"Team Development": "Up to 6",
				"Retreats & Offsites": "Up to 20"
			}
		},
		{
			name: "Operational & planning support",
			tiers: {
				"1:1 Coaching": false,
				"Team Development": true,
				"Retreats & Offsites": true
			}
		},
		{
			name: "On-demand contact",
			tiers: {
				"1:1 Coaching": "Optional email check-in",
				"Team Development": "Ongoing support",
				"Retreats & Offsites": "Full support before & during"
			}
		}
	],
		tiers = [
		{
			name: "1:1 Coaching",
			monthlyPrice: null,
			yearlyPrice: null,
			description: "Personal coaching partnership for individuals seeking growth, clarity, or a new approach."
			features: [
				"Includes 4–6 coaching sessions (80 minutes each)",
				"Zoom or in-person (Berlin)",
				"Free chemistry call",
				"Custom goals and pacing",
				"Reflection & feedback in final session"
			],
			cta: {
				label: "Book your first session",
				href: "mailto:hello@wahala.work?subject=1:1 Coaching inquiry"
			}
		},
		{
			name: "Team Development",
			monthlyPrice: null,
			yearlyPrice: null,
			description: "A structured coaching and facilitation program for leadership teams to strengthen culture and performance over 3–6 months.",
			features: [
				"Custom-designed program (3–6 months)",
				"Best for teams up to 6",
				"Individual and group sessions",
				"Onsite, Zoom, or hybrid format",
				"Team reflection session included",
				"Starts with a free alignment call"
			],
			cta: {
				label: "Request a team proposal",
				href: "mailto:hello@wahala.work?subject=Team Development inquiry"
			},
			highlight: true
		},
		{
			name: "Retreats & Offsites",
			monthlyPrice: null,
			yearlyPrice: null,
			description: "Bespoke offsites to reconnect, reflect, and make momentum as a team. Fully facilitated, customized, and seamlessly delivered.",
			features: [
				"Hosted for up to 20 people",
				"Goal alignment/planning support",
				"Tailored agenda (work/rest/activities)",
				"Onsite facilitation",
				"External experience providers optional",
				"Pricing custom for each team"
			],
			cta: {
				label: "Plan your retreat",
				href: "mailto:hello@wahala.work?subject=Retreat/Offsite planning inquiry"
			}
		}
	]
	}: {
		title?: string;
		subtitle?: string;
		tiers?: PricingTier[];
		features?: PricingFeature[];
		tierNames?: string[];
		caption?: string;
	} = $props();

	// State
	let annual = $state(true);
</script>

<section class="section-py section-px container mx-auto">
	<div class="flex flex-col items-baseline justify-between lg:flex-row">
		<SectionHeader {title} {subtitle} />

		<div class="mb-8 flex justify-center">
			<div class="inline-flex items-center rounded-full bg-gray-100 p-0.5 dark:bg-gray-800">
				<Button
					variant="ghost"
					size="sm"
					class=" {!annual ? 'bg-white shadow-sm dark:bg-gray-700' : ''}"
					onclick={() => (annual = false)}
				>
					Monthly
				</Button>
				<Button
					variant="ghost"
					size="sm"
					rounded
					class={annual ? "bg-white shadow-sm dark:bg-gray-700" : ""}
					onclick={() => (annual = true)}
				>
					Annual <span class="text-primary-600 dark:text-primary-400 text-footnote">Save 20%</span>
				</Button>
			</div>
		</div>
	</div>

	<div class="bb grid gap-6 md:grid-cols-2 lg:grid-cols-3">
		{#each tiers as tier}
			<div
				class="flex flex-col rounded-xl bg-white p-6 ring ring-gray-200 transition-all duration-300 dark:bg-gray-800 dark:ring-gray-700"
				class:ring-2={tier.highlight}
				class:ring-primary={tier.highlight}
				class:dark:ring-primary-700={tier.highlight}
				class:translate-y-[-4px]={tier.highlight}
			>
				<div class="mb-8">
					<h3 class="text-title3 mb-4 dark:text-white">{tier.name}</h3>
					<div class="mt-2 flex items-baseline">
						{#if tier.monthlyPrice === null && tier.yearlyPrice === null}
							<span class="text-title2 dark:text-white">Custom</span>
						{:else}
							<NumberFlow
								class="text-title2 [&::part\(suffix\)]:text-caption dark:text-white"
								format={{
									style: "currency",
									currency: "USD",
									trailingZeroDisplay: "stripIfInteger"
								}}
								value={annual ? tier.yearlyPrice : tier.monthlyPrice}
								suffix="/month"
							/>
						{/if}
					</div>
					<p class="text-callout text-emphasis-medium mt-3 dark:text-gray-300">
						{tier.description}
					</p>
				</div>

				<div class="mb-8 flex-grow">
					<ul class="space-y-3">
						{#each tier.features as feature}
							<li class="flex items-center gap-2">
								<IconCheck class="text-primary-600 dark:text-primary-400 size-5 flex-shrink-0" />
								<span class="text-body text-emphasis-medium dark:text-gray-300">{feature}</span>
							</li>
						{/each}
					</ul>
				</div>

				<div class="mt-auto">
					<Button
						href={tier.cta.href}
						variant={tier.highlight ? "primary" : "secondary"}
						class="w-full"
					>
						{tier.cta.label}
					</Button>
				</div>
			</div>
		{/each}
	</div>
	<div class="mt-32">
		<!-- Responsive table wrapper with horizontal scroll on mobile -->
		<!-- <div class=" hidden overflow-x-auto px-4 sm:mx-0 sm:block sm:px-0">
			<table
				class="w-full min-w-full border-separate border-spacing-0 border-gray-200 text-left dark:border-gray-700"
			>
				<thead>
					<tr>
						<th
							class="sticky left-0 min-w-[120px] border-b border-gray-200 bg-white dark:border-gray-700 dark:bg-gray-900"
						>
							<span class="sr-only">Feature</span>
						</th>
						{#each tierNames as tierName}
							<th
								class="text-headline min-w-[100px] border-b border-gray-200 p-4 text-start font-normal dark:border-gray-700"
							>
								{tierName}
							</th>
						{/each}
					</tr>
				</thead>
				<tbody>
					{#each features as feature}
						<tr>
							<td class="text-caption">
								{feature.name}
							</td>
							{#each tierNames as tierName}
								<td
									class="min-w-[100px] border-b border-gray-200 p-4 text-start text-gray-600 dark:border-gray-700 dark:text-gray-300"
								>
									{#if typeof feature.tiers[tierName] === "boolean"}
										{#if feature.tiers[tierName]}
											<IconCheck
												class="text-primary-600 dark:text-primary-400 mx-auto size-5 sm:mx-0"
											/>
										{:else}
											<IconX class="mx-auto size-5 text-gray-400 sm:mx-0" />
										{/if}
									{:else}
										{feature.tiers[tierName]}
									{/if}
								</td>
							{/each}
						</tr>
					{/each}
				</tbody>
			</table>
		</div> -->

		<!-- Mobile feature comparison (alternative view for very small screens) -->
		<div>
			<!-- Universal pricing comparison for mobile -->
			<div class="overflow-x-auto">
				<table class="w-full border-collapse">
					<!-- Sticky header with tier names -->
					<thead class="border-border sticky top-0 z-10 border-b">
						<tr>
							<th class="min-w-[120px] py-3 text-left">
								<span class="sr-only">Feature</span>
							</th>
							{#each tierNames as tierName, i}
								<th class="text-caption min-w-[100px] py-3 text-left dark:text-white">
									{tierName}
								</th>
							{/each}
						</tr>
					</thead>
					<tbody class="divide-border divide-y">
						{#each features as feature}
							<tr>
								<td class="text-body py-3 pr-8 font-medium lg:pr-0 dark:text-white">
									{feature.name}
								</td>
								{#each tierNames as tierName, i}
									<td class="py-3">
										{#if typeof feature.tiers[tierName] === "boolean"}
											{#if feature.tiers[tierName]}
												<IconCheck class="text-primary-900 dark:text-primary-400 size-5" />
											{:else}
												<IconX class="size-5 text-gray-400" />
											{/if}
										{:else}
											<span class="text-callout font-medium text-gray-700 dark:text-gray-300">
												{feature.tiers[tierName]}
											</span>
										{/if}
									</td>
								{/each}
							</tr>
						{/each}
					</tbody>
				</table>
			</div>
		</div>
	</div>
	<LogoScroller />
</section>

<style lang="postcss">
	@reference '../../../app.css';

	:global(number-flow-svelte)::part(suffix) {
		@apply text-sm text-gray-400 dark:text-gray-500;
	}
</style>
