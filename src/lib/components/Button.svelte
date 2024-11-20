<script>
	import { loadStripe } from '@stripe/stripe-js';
	import { PUBLIC_STRIPE_KEY } from '$env/static/public';
	import { goto } from '$app/navigation';

	let { children, ...props } = $props();

	async function onclick() {
		try {
			const stripe = await loadStripe(PUBLIC_STRIPE_KEY);

			const res = await fetch('/api/checkout', {
				method: 'POST',
				headers: {
					'Content-Type': 'application/json'
				}
			});

			const { sessionId } = await res.json();

			await stripe.redirectToCheckout({ sessionId });
		} catch (err) {
			goto('/checkout/failure');
		}
	}
</script>

<button {...props} {onclick}>{@render children()}</button>

<style>
	button {
		background-color: #000;
		color: #fff;
		padding: 1.2rem 1.8rem;
		font-size: 1.2rem;
		text-transform: uppercase;
		transition: all 0.22s ease;
		border: 1px solid #fff;
		&:hover {
			background-color: #fff;
			color: #000;
		}
	}
</style>
