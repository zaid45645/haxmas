<script lang="ts">
	export let href: string | undefined = undefined;
	export let color: string = '#2196f3';
	export let className: string = '';

	let currentBg = color;
</script>

{#if href}
	<a {href} class={className} style="text-decoration: none; color: inherit;">
		<button
			class="btn"
			style="background-color: {currentBg};"
			on:mouseover={() => (currentBg = '#1976d2')}
			on:mouseout={() => (currentBg = color)}
			on:focus={() => (currentBg = '#1976d2')}
			on:blur={() => (currentBg = color)}
		>
			<slot />
		</button>
	</a>
{:else}
	<button
		class="btn {className}"
		style="background-color: {currentBg};"
		on:click
		on:mouseover={() => (currentBg = '#1976d2')}
		on:mouseout={() => (currentBg = color)}
		on:focus={() => (currentBg = '#1976d2')}
		on:blur={() => (currentBg = color)}
	>
		<slot />
	</button>
{/if}

<style>
	.btn {
		padding: 10px 24px;
		border-radius: 8px;
		border: 2px solid #1976d2;
		color: white;
		font-weight: 500;
		font-size: 1rem;
		cursor: pointer;
		transition: background 0.2s;
		pointer-events: all;
		white-space: nowrap;
	}

	@media (max-width: 768px) {
		.btn {
			padding: 8px 18px;
			font-size: 0.9rem;
		}
	}

	@media (max-width: 480px) {
		.btn {
			padding: 6px 14px;
			font-size: 0.85rem;
		}
	}
</style>
