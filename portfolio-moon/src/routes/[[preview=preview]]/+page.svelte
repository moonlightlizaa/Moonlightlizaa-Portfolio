<script>
	import { SliceZone } from '@prismicio/svelte';

	import { components } from '$lib/slices';

	export let data;
</script>

<!-- home page -->

<SliceZone slices={data.page.data.slices} {components} />
