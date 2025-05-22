<script>
	let { title = "", description = "", class: customClass = "" } = $props();
</script>

<article
	class="bg-white/50 grid content-between gap-16 rounded-(--radius) p-4 px-5 text-pretty shadow-[0_4px_24px_0_rgba(188,144,84,0.10)] transition duration-300 ease-out lg:p-5 lg:px-6 {customClass}"
>
	<h3 class="text-title3 mb-2">
		{title}
	</h3>
	<p class="text-body max-w-prose opacity-60">{description}</p>
</article>
