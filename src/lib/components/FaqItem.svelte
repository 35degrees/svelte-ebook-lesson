<script>
	let { faq, isExpanded, ...props } = $props();
</script>

<button class="container" class:expanded={isExpanded} {...props}>
	<div class="question-answer">
		<p class="question mb-s">{faq.question}</p>
		<p class="answer">
			{faq.answer}
		</p>
	</div>
	<img
		src="https://raw.githubusercontent.com/35degrees/svelte-ebook-lesson/a2d196e3e2ad883944f4ac3fc6556da369767183/src/assets/icons/chevron-down.svg"
		alt="chevron icon"
	/>
</button>

<style>
	.container {
		display: flex;
		justify-content: space-between;
		align-items: flex-start;
		padding: 1rem 0;
		border-bottom: 1px solid rgba(0, 0, 0, 0.2);
		text-align: left;
	}
	.answer {
		max-height: 0;
		overflow: hidden;
		opacity: 0;
		transition:
			max-height 0.3s ease-out,
			opacity 0.24s ease-out;
	}

	.question-answer {
		padding-right: 10rem;
		flex-grow: 1;
	}

	button img {
		width: 1.5rem;
		height: 1.5rem;
		transition: transform 0.3s linear;
	}

	.question {
		font-weight: 600;
	}

	/* expanded  */

	.expanded img {
		transform: rotate(180deg);
	}

	.expanded .answer {
		max-height: unset;
		opacity: 0.5;
		font-size: 1.2rem;
	}
</style>
