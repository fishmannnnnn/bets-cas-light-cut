<template>
	<div class="data-bg">
		<div class="data">
			<img :src="getImageUrl(data.imgName)" class="event-img" />
			<svg
				v-if="!data.unclosable"
				class="btn-close"
				width="20"
				height="20"
				viewBox="0 0 20 20"
				fill="none"
				xmlns="http://www.w3.org/2000/svg">
				<path
					d="M15 5L5 15"
					stroke="#5E6471"
					stroke-width="1.5"
					stroke-linecap="round"
					stroke-linejoin="round" />
				<path
					d="M5 5L15 15"
					stroke="#5E6471"
					stroke-width="1.5"
					stroke-linecap="round"
					stroke-linejoin="round" />
			</svg>
			<div class="id">{{ data.id }}</div>
			<div class="container-coef">
				<div class="container-teams-coefname">
					<div class="teams">
						{{ data.teams }}
					</div>
					<div class="coefname">{{ data.coefName }}</div>
				</div>
				<div :class="['coef', isRed ? 'coef-red' : '']">
					{{ data.coef }}
				</div>
			</div>
		</div>
	</div>
</template>

<script setup>
	defineProps({
		data: Object,
		isRed: Boolean,
	});
	const getImageUrl = (name) =>
		new URL(`/src/assets/events-icons/${name}.png`, import.meta.url).href;
</script>

<style lang="scss" scoped>
	@import '@/styles/global';
	.event-img {
		position: absolute;
		top: 0;
		left: 0;
		transform: translate(-25%, -25%);
	}
	.btn-close {
		position: absolute;
		top: 0;
		right: 0;
	}
	.data-bg {
		border-radius: 4px;
		padding: 1px;
		background: white;
		box-shadow: 0 0 2px rgba(0, 0, 0, 0.25);
	}
	.data {
		border-radius: 3px;
		padding: 8px 15px 0;
		background: $bg-white;
		height: 66px;
		width: 100%;
		gap: 5px;
		position: relative;
	}
	.id {
		font: $h7-regular;
		color: $gray-text;
	}
	.container-teams-coef {
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.teams {
		font: $h5-regular;
		color: $text-dark;
	}
	.container-coef {
		display: flex;
		align-items: center;
		justify-content: space-between;
		color: $text-dark;
	}
	.coefname {
		font: $h7-regular;
	}
	.coef {
		font: $h4-medium;
	}
	.coef-red {
		color: $red-validation;
	}
</style>
