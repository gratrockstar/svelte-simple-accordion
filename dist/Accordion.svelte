<script>

  // import from context.
	import { setAccordionOptions } from './context';

  // by default more than one accordion can be open.
  export let collapse = false;

  // the context API avoids passing data through components as props.
  setAccordionOptions({ collapse });
</script>

<div class="accordion">
  <slot />
</div>

<style>
.accordion {
  width: var(--accordion-width, 100%);
  padding: var(--accordion-padding, 0);
  color: var(--accordion-color, #000);
  background-color: var(--accordion-background, transparent);
  border-radius: var(--accordion-radius, 2px);
  box-shadow: var(--accordion-shadow);
}
</style>