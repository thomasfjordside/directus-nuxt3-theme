<template>
	<NuxtLink
		:to="`${post.ctaLink}`"
		:target="post.type == 'article' ? '_self' : '_blank'"
		:class="[
			'c-card overflow-hidden transition-all duration-300 bg-color text-primary transform  hover:shadow-xl',
		]"
	>
		<div class="c-card__image-container">
			<nuxt-picture
				v-if="post.heroImage"
				:src="`https://data.cassette.cc/assets/${post.heroImage}`"
				sizes="sm:100vw md:50vw lg:1024px"
			/>
		</div>
		<div class="p-25">
			<p class="mb-8 text-xs font-semibold">
				{{ new Date(post.publish_time).toLocaleDateString() }}
			</p>
			<div
				class="inline-block mb-10 transition-colors duration-200 hover:text-deep-purple-accent-700"
			>
				<h2
					:class="[
						'font-bold ',
						{
							'text-h3': post.heroImage,
							'text-h2': !post.heroImage,
						},
					]"
				>
					{{ post.title }}
				</h2>
			</div>
			<p class="mb-8">{{ post.teaser }}</p>
		</div>
	</NuxtLink>
</template>

<script setup>
defineProps({
	post: Object,
});
</script>

<style>
.c-card img {
	object-fit: cover;
	width: 100%;
	height: 100%;
}
/* .c-grid-mosaic .c-card--0 {
	@apply col-span-2 row-span-2;
} */
.c-card__image-container {
	aspect-ratio: 16/9;
}
/* .c-grid-mosaic .c-card--3 {
	@apply col-span-1 row-span-2;
}
.c-grid-mosaic .c-card--9 {
	@apply col-span-2 row-span-1;
} */
</style>
