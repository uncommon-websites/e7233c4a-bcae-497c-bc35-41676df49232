<script lang="ts">
	// Components
	import CallToAction from "$lib/components/layout/CallToAction.svelte";

	// Icons
	import StakeholderGrid from "$lib/components/layout/StakeholderGrid.svelte";
	import Story from "./Story.svelte";
	import SecondaryHero from "$lib/components/layout/hero-sections/SecondaryHero.svelte";
	import Culture from "$lib/components/layout/Culture.svelte";

	// Constants
	const values = [
  {
    title: "Rewrite your story",
    description:
      "We help you let go of old scripts and shape a narrative that actually fits—whether for yourself or your team. Change starts with a new story."
  },
  {
    title: "Gather with intention",
    description:
      "We create welcoming spaces for honest reflection and connection. Growth takes root when you feel safe, seen, and able to share what’s real."
  },
  {
    title: "Grow honestly, together",
    description:
      "Progress isn’t just about achievement—it’s about working through the messy bits. We challenge with kindness and support you in making change that feels true to you."
  }
];
</script>

<SecondaryHero
	title="Rewrite your story, grow with purpose"
	subtitle="Coaching and experiences for individuals and teams to grow, connect, and lead with clarity"
	imageSrc="/generated/image-a-diverse-group-of-professionals-gathere.webp"
/>

<!-- Story Section -->
<Story
	paragraphs={[
		"Wahala began with a simple idea: the stories we believe—about ourselves or our teams—can be rewritten. After years spent building teams in law, the art world, startups, and venture capital, I realized that real change starts by resetting the narrative, not just the goals.",
		"Instead of chasing someone else’s definition of success, Wahala helps individuals and teams reconnect with what matters. Through coaching, guided conversation, and designing thoughtful ways to gather, we make room for honest reflection and authentic progress.",
		"My friends call me Mamma Mia because I love to host and help people feel at ease. That care is the heart of Wahala. Today, I work with those seeking clarity, new direction, or simply a better way of working together—so more people can finally move forward in a way that feels true to them."
	]}
/>

<!-- Our Culture Section -->
<Culture {values} />

<!-- StakeholderGrid Section -->
<StakeholderGrid
  stakeholderType="team"
  title="Meet your partner"
  subtitle="Coaching and experiences led by:"
  stakeholders={[
    {
      name: "Mamma Mia",
      position: "Founder, Coach & Experience Designer",
      bio: "After a career in law, the art world, startups, and VC People & Talent, I founded Wahala to help others rewrite their stories and move forward with more ease and clarity. Youll find me designing thoughtful spaces for growth—and always cheering you on.",
      image: "/generated/image-a-female-founder-in-a-modern-headshot-ex.webp"
    }
  ]}
/>

 

<!-- CTA Section -->
<CallToAction
	title="Let’s start with a conversation"
	subtitle="Book a free chemistry call or intro session"
	description="No pressure, no sales pitch—just a safe space to ask questions, get clarity, and see if Wahala feels like the right fit for your growth journey. If you’re feeling curious or want to talk through where you’re at, let’s connect."
	callsToAction={[
		{ href: 'mailto:hello@wahala.coach', label: 'Book a chemistry call', variant: 'primary' },
		{ href: 'mailto:hello@wahala.coach', label: 'Get in touch', variant: 'secondary' }
	]}
/>
