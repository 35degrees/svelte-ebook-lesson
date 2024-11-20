<script>
	import { FaqItem, Button } from '$components';

	const faqs = [
		{
			question: 'What will I learn from this ebook?',
			answer:
				"This ebook provides a comprehensive guide to relocating to Spain, covering everything from securing the right visa and navigating Spain's legal system to finding the perfect place to live and integrating into the local culture. Whether you're moving for work, study, or retirement, this guide equips you with the essential knowledge and practical steps to make your transition as smooth as possible."
		},
		{
			question: 'Who is this ebook for?',
			answer:
				"This ebook is perfect for anyone considering a move to Spain, whether you're planning a short-term stay or a permanent relocation. It's designed for expats, retirees, students, and professionals who want to avoid common pitfalls and streamline their move. If you're looking for a detailed, step-by-step guide to help you every step of the way, this ebook is for you."
		},
		{
			question: 'How much does the ebook cost?',
			answer:
				'The ebook is priced at $10. This one-time purchase grants you immediate access to all the content, including detailed chapters, actionable checklists, and valuable resources that will save you time, money, and stress during your move to Spain.'
		},
		{
			question: 'Is the information in the ebook up-to-date?',
			answer:
				"Yes, the ebook is regularly updated to reflect the latest changes in Spanish immigration laws, visa requirements, and other relevant information. The author, John Smith, stays on top of these updates to ensure that you're receiving the most accurate and current guidance available."
		},
		{
			question: "Can I get a refund if I'm not satisfied?",
			answer:
				"Absolutely. We offer a 30-day money-back guarantee. If you feel that the ebook did not meet your expectations or didn't provide the value you were looking for, simply contact us within 30 days of your purchase, and we’ll issue a full refund—no questions asked."
		}
	];
	let questionExpanded = $state(-1);

	function onclick(i) {
		i === questionExpanded ? (questionExpanded = -1) : (questionExpanded = i);
	}
</script>

<section class="landing-page-section">
	<h2 class="mb-l">Frequently Asked Questions</h2>
	<div class="faq-container">
		{#each faqs as faq, i}
			<FaqItem {faq} isExpanded={i === questionExpanded} onclick={() => onclick(i)} />
		{/each}
	</div>
	<div class="additional-info mt-m">
		<Button class="mt-5">Buy Now</Button>
		<p class="mt-m">Any other questions?</p>

		<a href="https://x.com/KIZO_ES">
			<p class="tw">
				Hit me up on Twitter <img
					src="https://raw.githubusercontent.com/35degrees/svelte-ebook-lesson/refs/heads/main/src/assets/icons/twitter.webp"
					class="twitter-icon"
					alt=""
				/>
			</p></a
		>
	</div>
</section>

<style>
	.additional-info {
		display: flex;
		flex-direction: column;
		align-items: center;
		color: gray;
	}

	.additional-info a {
		text-decoration: underline;
	}

	.twitter-icon {
		width: 1rem;
		object-fit: contain;
		margin-left: 0.2rem;
	}
	.tw {
		display: flex;
		flex-direction: row;
		gap: 9;
	}
</style>
