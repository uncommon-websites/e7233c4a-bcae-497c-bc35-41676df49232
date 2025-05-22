<script lang="ts">
	// Types
	import type { PageProps } from "./$types";

	// Components
	import Features from "$lib/components/layout/Features.svelte";
	import Testimonials from "$lib/components/layout/Testimonials.svelte";
	import CallToAction from "$lib/components/layout/CallToAction.svelte";
	import Pricing from "$lib/components/layout/Pricing.svelte";

	// Props
	const { data }: PageProps = $props();
</script>

<Pricing />

<Testimonials
  testimonials={[
    {
      name: "Afsana Hewitt",
      position: "head of people",
      company: "Soundra Tech",
      quote:
        "Our engagement surveys improved by over 35% after our six-month coaching program with Wahala. It just worked—easy to set up, deeply impactful, and well worth the cost.",
      image: "/generated/image-a-confident-black-woman-in-a-professiona.webp"
    },
    {
      name: "Kota Misaki",
      position: "co-founder",
      company: "Hako Health",
      quote:
        "As a founder, time and budget are always top of mind. Wahala was thoughtful, agile, and honest throughout—and the clarity I gained saved me months of wasted effort.",
      image: "/generated/image-a-southeast-asian-man-in-a-modern-worksp.webp"
    },
    {
      name: "Yara Tilling",
      position: "VP engineering",
      company: "Renuvia",
      quote:
        "We were skeptical about the ROI of another offsite—but two weeks later our exec meetings felt transformed. People listened more, got aligned faster, and decisions stuck. It paid off fast.",
      image: "/generated/image-a-hispanic-woman-founder-in-a-dynamic-st.webp"
    }
  ]}
/>

<CallToAction
  title="Work doesn’t have to be this hard"
  subtitle="Let’s make space for something better"
  description="At Wahala, we help individuals and teams shift the stories that shape their lives. Through coaching and experience design, we create space to pause, reflect, and reimagine how you work—so it feels more aligned, sustainable, and meaningful. Ready to bring more clarity and cohesion— to your leadership, team, or next chapter? Let’s start the conversation."
  imageSrc="/generated/image-a-cheerful-professional-sitting-at-a-woo.webp"
  callsToAction={[
    {
      href: '/contact',
      label: 'Start a conversation',
      variant: 'primary'
    }
  ]}
/>

