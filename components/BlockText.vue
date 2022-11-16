<template>
	<div class="c-block-text w-6col mx-auto my-lg">
		<div
			class="c-block-text__content text-body text-gray-700"
			v-html="item.text"
		></div>
	</div>
</template>

<script setup>
defineProps({
	item: Object,
});
</script>