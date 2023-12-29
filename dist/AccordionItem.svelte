<script>
  import { slide } from 'svelte/transition';
	import { getAccordionOptions } from './context';

	// by default the accordion item is closed
	export let open = false;

	// assign a unique identifier for the component
	const componentId = crypto.randomUUID();

	// get the accordion options using the context api
	const { collapse, activeComponentId } = getAccordionOptions();

	function setActive() {
		// update the store value in the context
		$activeComponentId = componentId;
	}

	function toggleOpen() {
		open = !open;
	}

	function handleClick() {
		// if `collapse` is passed only one item can be active
		collapse ? setActive() : toggleOpen();
	}

	// the accordion item to be open by default
	$: open && collapse && setActive();
	// compare if the active id matches the component id
	$: isActive = $activeComponentId === componentId;
	// if `collapse`, set one item as active, otherwise use `open`
	$: isOpen = collapse ? isActive : open;
</script>

<div class="accordion-item">
	<button
		on:click={handleClick}
		class="accordion-toggle"
		aria-expanded={isOpen}
		aria-controls="accordion-{componentId}"
	>
		<div class="accordion-title">
			<slot name="title" />
		</div>
	</button>

	{#if isOpen}
		<!-- local transitions only play when the block they belong to is created or destroyed -->
		<div
			transition:slide|local
			class="accordion-content"
			role="region"
			aria-hidden={!isOpen}
			aria-labelledby="accordion-{componentId}"
		>
			<slot name="content" />
		</div>
	{/if}
</div>

<style>
	.accordion-toggle {
		width: 100%;
		display: flex;
		justify-content: space-between;
		padding: var(--accordion-padding, 1rem);
		color: var(--accordion-color, #000);
		font: inherit;
		font-weight: 600;
		border: none;
		background: var( --accordion-toggle-bg, rgba(0,0,0,.2) );
		cursor: pointer;
		border-radius: var(--accordion-radius, 4px);
		transition: background-color 0.1s ease;
	}
	.accordion-toggle:hover {
		background-color: var(--accordion-hover, rgba(0,0,0,.3));
	}

	.accordion-content {
		padding: var(--accordion-content-padding, 1rem);
	}
</style>