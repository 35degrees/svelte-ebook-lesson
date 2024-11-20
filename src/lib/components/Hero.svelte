<script>
	import bookCover from '$assets/book_cover.png';
	import phoneCover from '$assets/phone_cover.png';
	import { Button } from '$components';

	let { children } = $props();
</script>

<section class="hero select-none">
	<div class="hero-showcase bold text-center">
		<h1 class="purple">MOVE TO</h1>
		<h1 class="purple mb-xs">SPAIN</h1>
		<h4 class="semi-bold italic">There's no need to make the same mistakes I made.</h4>
		<img class="book-cover" src={bookCover} alt="" />
		<img class="phone-cover" src={phoneCover} alt="" />
	</div>

	<div class="hero-text text-center text-white">
		{#if children}
			{@render children()}
		{:else}
			<h1>THIS EBOOK WILL</h1>
			<h1>SAVE YOU MONEY</h1>
			<h1 class="md-m">TIME & NERVES</h1>
			<p class="light-grey mb-l">
				I moved to Spain seven years ago. The process was painful and difficult. I learned most
				things the hard way: finding a job, getting a visa, calculating my cost of living, choosing
				an apartment. That's why I wrote this e-book, to tell you how I did it. No bullshit, no
				stress.
			</p>
			<Button>Purchase eBook for $10</Button>
		{/if}
	</div>
</section>

<style>
	.hero {
		display: flex;
		height: 100vh;
		overflow-y: hidden;
	}

	.hero-showcase {
		position: relative;
		width: 50%;
		padding: 100px 16px 0 16px;
		background: linear-gradient(135deg, #e2cbff, #e2cbff 25%, #d2cbff 50%, #ece5ff 75%, #927bce);
	}

	.hero-text {
		padding: 100px 5%;
		width: 50%;
		background-color: #000;
		user-select: none;
	}

	.book-cover {
		position: absolute;
		right: 2%;
		bottom: 0;
		width: 65%;
		transform: translateY(30%);
	}

	.phone-cover {
		width: 35%;
		position: absolute;
		bottom: 0;
		right: 52%;
		transform: translateY(35%);
	}
</style>
