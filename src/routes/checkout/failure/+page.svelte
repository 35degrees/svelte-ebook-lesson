<script>
	import { Hero } from '$components';
	import Button from '$components/Button.svelte';
</script>

<Hero>
	<h1>I'm sorry, it</h1>
	<h1 class="mb-10">didn't go through.</h1>
	<p class="light-grey mb-s">
		We’re sorry, but it looks like there was an issue with your purchase. Don’t worry—these things
		happen, and we're here to help.Please double-check your payment details and try again.
	</p>
	<p class="light-grey mb-s">
		We apologize for any inconvenience this may have caused and appreciate your patience. We’re
		committed to ensuring that you get the guide you need to make your move to Spain as smooth as
		possible.
	</p>
	<p class="light-grey mb-m">
		If you’d like to try again, please click the button below to return to the checkout page.
	</p>
	<Button>Try Again</Button>
</Hero>
