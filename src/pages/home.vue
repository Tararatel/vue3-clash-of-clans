<template>
	<carousel :settings="settings" :breakpoints="breakpoints">
		<slide class="card__wrapper" v-for="item in items" :key="item.id">
			<Card :name="`${item.lvl} lvl`" :title="item.title" :imgUrl="item.img" :link="`/${item.alias}`">
				<template v-slot:body>{{ item.description }} </template>
				<Stats />
			</Card>
		</slide>
		<template #addons>
			<navigation />
		</template>
	</carousel>
</template>

<script>
import Card from '@/components/UI/Card.vue';
import Stats from '@/components/Stats.vue';
import items from '@/seeders/items.js';
import 'vue3-carousel/dist/carousel.css';
import { Carousel, Slide, Navigation } from 'vue3-carousel';
export default {
	components: { Card, Stats, Carousel, Slide, Navigation },
	data() {
		return {
			items: items,
			settings: {
				itemsToShow: 4,
				wrapAround: true,
				snapAlign: 'center',
			},
			breakpoints: {
				300: {
					itemsToShow: 1,
				},
				700: {
					itemsToShow: 3,
				},
			},
		};
	},
};
</script>
