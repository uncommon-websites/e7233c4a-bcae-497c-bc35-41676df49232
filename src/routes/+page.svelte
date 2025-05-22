<script lang="ts">
	// Components
	import UseCases from "$lib/components/layout/UseCases.svelte";
	import Summary from "$lib/components/layout/Summary.svelte";
	import Features from "$lib/components/layout/Features.svelte";
	import Testimonials from "$lib/components/layout/Testimonials.svelte";
	import CallToAction from "$lib/components/layout/CallToAction.svelte";
	import AboutTeaser from "$lib/components/layout/AboutTeaser.svelte";
	import LogoScroller from "$lib/components/layout/LogoScroller.svelte";
	import CustomerCardHero from "$lib/components/layout/hero-sections/CustomerCardHero.svelte";
</script>

<CustomerCardHero
  centered={true}
  title="Rewrite your story to grow with purpose"
  subtitle="Coaching and team experiences that help you reflect, reconnect, and lead with clarity—personally and together."
  customers={[
    {
      name: "Anna Müller",
      position: "Head of People, TerraLabs",
      imageSrc: "/generated/image-a-professional-european-woman-leader-ele.webp",
      bio: "Working with Wahala helped me rethink what great leadership looks like—for myself and across our team."
    },
    {
      name: "Diego Fernández",
      position: "CTO, BrightChain",
      imageSrc: "/generated/image-a-professional-latino-man-dressed-in-bus.webp",
      bio: "The sessions gave me the insight and clarity I hadn’t been able to find in any other professional development setting."
    },
    {
      name: "Aisha Campbell",
      position: "Startup founder, Woven",
      imageSrc: "/generated/image-a-young-black-woman-startup-founder-dres.webp",
      bio: "I feel more grounded in how I show up for my team—and braver about what we’re building."
    },
    {
      name: "Louise Tremblay",
      position: "Partner, Nova VC",
      imageSrc: "/generated/image-a-professional-french-woman-a-venture-ca.webp",
      bio: "Our offsite with Wahala brought an ease and depth to our team we hadn't found in years of working together."
    },
    {
      name: "Tomoko Ichikawa",
      position: "People operations lead, Orchard",
      imageSrc: "/generated/image-a-japanese-woman-a-people-operations-lea.webp",
      bio: "Wahala created space for honest conversations that helped us reconnect as a leadership team."
    }
  ]}
/>
<LogoScroller label="Trusted by industry leaders" logoUrls={[
  'https://logo.clearbit.com/airbnb.com',
  'https://logo.clearbit.com/stripe.com',
  'https://logo.clearbit.com/hopin.com',
  'https://logo.clearbit.com/elastic.co'
]} />

<Summary
	title="What we do"
	text="Wahala provides coaching and curated experiences to help individuals and teams grow with intention. We create space for honest reflection and new ways of leading, working, and connecting."
/>

<Testimonials
	testimonials={[
		{
			name: "Isabelle Thorpe",
			position: "Founder & CEO",
			company: "Commonspring",
			quote:
				"As a founder juggling team growth and investor meetings, Wahala’s coaching helped me reclaim almost 10 hours per week by creating space to set better boundaries and reset priorities. That time now goes back into company-building — not burnout.",
			image:
				"/generated/image-a-confident-woman-standing-on-a-rooftop-.webp"
		},
		{
			name: "Marcus Elanders",
			position: "CFO",
			company: "Northtrace Technologies",
			quote:
				"Wahala supported us through a challenging team restructuring. As a CFO, I saw a clear drop in organizational risk — fewer resignations, smoother transitions, and stronger trust on the exec team. The impact showed up everywhere from morale to compliance.",
			image:
				"/generated/image-a-focused-man-in-a-high-rise-office-stan.webp"
		},
		{
			name: "Jamie Duarte",
			position: "COO",
			company: "Lucent Bioware",
			quote:
				"Bringing Wahala in saved us over €75k in misaligned hiring and retrying product strategy retreats. As a nonbinary COO, I valued how deeply human the process was — and how that clarity translated directly into smart decisions and real savings.",
			image:
				"/generated/image-a-nonbinary-person-in-a-shared-workspace.webp"
		}
	]}
/>

<Features
  title="How Wahala helps you grow"
  subtitle="Coaching and team experiences that support real change and connection—no matter where you start."
  features={[
    {
      title: "Coaching for individuals",
      description: "Work 1:1 to reflect, get unstuck, and grow on your terms—not someone else’s playbook."
    },
    {
      title: "Leadership team coaching",
      description: "Build culture, trust, and honest communication in your most important rooms."
    },
    {
      title: "Team offsites & retreats",
      description: "Thoughtfully designed gatherings that bring teams closer, refresh focus, and energize real collaboration."
    },
    {
      title: "A narrative approach",
      description: "We help you rewrite the stories that drive how you lead, build, and connect—with yourself and others."
    },
    {
      title: "Experience from VC and startups",
      description: "Wahala is led by a founder with roots in law, art, startups, and top VC People & Talent. Craft is built-in."
    },
    {
      title: "Human, not corporate",
      description: "No buzzwords, just space built for honesty, care, and practical growth—done together."
    }
  ]}
/>

<UseCases
  title="Use Cases"
  subtitle="Real-world applications for your business needs"
  useCases={[
    {
      title: "Coaching for rising leaders",
      description:
        "Designed for high-potential professionals taking on more responsibility, fast. We create space to reflect, focus, and lead with greater intention and clarity.",
      image: "/generated/image-a-professional-woman-attentively-coachin.webp",
      link: {
        href: "/use-cases/high-potential-coaching",
        label: "Learn more"
      }
    },
    {
      title: "Team offsites that actually work",
      description:
        "Help your fast-growing team hit pause, reconnect, and get aligned. We handle the structure and flow so your people can focus on what matters most.",
      image: "/generated/image-a-diverse-and-energetic-startup-leadersh.webp",
      link: {
        href: "/use-cases/guided-startup-offsite",
        label: "Learn more"
      }
    },
    {
      title: "Executive narrative alignment",
      description:
        "VC-backed leadership teams often move quickly—sometimes without full alignment. We facilitate real-time narrative work to strengthen clarity, coherence, and trust across the top table.",
      image: "/generated/image-an-executive-team-deeply-engaged-in-a-st.webp",
      link: {
        href: "/use-cases/executive-narrative-facilitation",
        label: "Learn more"
      }
    }
  ]}
/>

<AboutTeaser />
<CallToAction
  title="Say yes to change"
  subtitle="Invest in the growth you want — for yourself or your team."
  description="Experience honest, human coaching that helps you or your team move forward with clarity, energy, and focus. Wahala creates space for meaningful growth—without the noise."
  imageSrc="/generated/image-a-cheerful-startup-team-leader-standing-.webp"
  callsToAction={[
    { href: '/contact', label: 'Book intro call', variant: 'primary' },
    { href: '/how-it-works', label: 'See how it works', variant: 'secondary' }
  ]}
/>
