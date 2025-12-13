<script lang="ts">
	interface Props {
		className?: string;
	}

	let { className = '' }: Props = $props();

	let isHovered = $state(false);
</script>

<a href="/auth/login" class={className} style="text-decoration: none; color: inherit;">
	<button
		class="login-btn"
		style="background-color: {isHovered ? '#c42e44' : '#ec3750'};"
		onmouseenter={() => (isHovered = true)}
		onmouseleave={() => (isHovered = false)}
		onfocus={() => (isHovered = true)}
		onblur={() => (isHovered = false)}
	>
		Log in with Hack Club
	</button>
</a>

<style>
	.login-btn {
		padding: 10px 24px;
		border-radius: 8px;
		border: 2px solid #ec3750;
		color: white;
		font-weight: 500;
		font-size: 1rem;
		cursor: pointer;
		transition: background 0.2s;
		pointer-events: all;
		white-space: nowrap;
	}

	@media (max-width: 768px) {
		.login-btn {
			padding: 8px 16px;
			font-size: 0.875rem;
		}
	}

	@media (max-width: 480px) {
		.login-btn {
			padding: 6px 12px;
			font-size: 0.8rem;
		}
	}
</style>
