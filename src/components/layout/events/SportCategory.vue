<script setup>
	import { ref } from "vue";
	const isComponentOpen = ref(false);
	const onClick = () => {
		isComponentOpen.value = !isComponentOpen.value;
	};
	defineProps({
		sport: String,
		league: String,
		shadowColor: String,
		imgName: String,
	});
	const getImageUrl = (name) => new URL(`/src/assets/events-icons/${name}.png`,import.meta.url).href;
</script>
<template>
	<div class="event" @click="onClick">
		<div class="event-bg">
			<img
				:src="getImageUrl(imgName)"
				class="event-img" />

			<div class="event-bg__rect-border">
				<div class="event-bg__rect"></div>
			</div>
			<div class="event-bg__right"></div>
			<div class="event__content">
				<div class="sport">{{ sport }}</div>
				<div class="container-right">
					<div class="league">{{ league }}</div>
					<svg
						v-if="isComponentOpen"
						class="arrow"
						width="10"
						height="6"
						viewBox="0 0 10 6"
						fill="none"
						xmlns="http://www.w3.org/2000/svg"
						version="1.1"
						xmlns:xlink="http://www.w3.org/1999/xlink"
						transform="matrix(1,0,0,-1,0,0)">
						<path
							fill-rule="evenodd"
							clip-rule="evenodd"
							d="M0.46967 0.46967C0.762563 0.176777 1.23744 0.176777 1.53033 0.46967L5 3.93934L8.46967 0.46967C8.76256 0.176777 9.23744 0.176777 9.53033 0.46967C9.82322 0.762563 9.82322 1.23744 9.53033 1.53033L5.53033 5.53033C5.23744 5.82322 4.76256 5.82322 4.46967 5.53033L0.46967 1.53033C0.176777 1.23744 0.176777 0.762563 0.46967 0.46967Z"
							fill="#3399E2"></path>
					</svg>
					<svg
						v-else
						class="arrow"
						width="10"
						height="6"
						viewBox="0 0 10 6"
						fill="none"
						xmlns="http://www.w3.org/2000/svg">
						<path
							fill-rule="evenodd"
							clip-rule="evenodd"
							d="M0.46967 0.46967C0.762563 0.176777 1.23744 0.176777 1.53033 0.46967L5 3.93934L8.46967 0.46967C8.76256 0.176777 9.23744 0.176777 9.53033 0.46967C9.82322 0.762563 9.82322 1.23744 9.53033 1.53033L5.53033 5.53033C5.23744 5.82322 4.76256 5.82322 4.46967 5.53033L0.46967 1.53033C0.176777 1.23744 0.176777 0.762563 0.46967 0.46967Z"
							fill="#3399E2" />
					</svg>
				</div>
			</div>
			<div :class="'shadow-' + shadowColor"></div>
		</div>
	</div>
	<div :class="['table-content', isComponentOpen ? 'table-visible' : '']">
		<slot></slot>
	</div>
</template>

<style lang="scss" scoped>
	@import "@/styles/global";
	.event {
		padding: 0 15px;
		height: 53px;
		position: relative;
		filter: drop-shadow(0px 4px 2px black);
	}
	.event-bg {
		position: relative;
		width: calc(100%);
	}
	.event-img {
		position: absolute;
		top: 0;
		left: 0;
		transform: translate(-25%, -25%);
		z-index: 30;
	}
	
	.event-bg__rect-border {
		height: 53px;
		width: calc(100% - 20px);
		padding: 1px 0 1px 1px;
		background: white;
		border-radius: 4px;
		border-top-right-radius: 0;
		border-bottom-right-radius: 0;
		position: relative;
		z-index: 20;
	}
	.event-bg__rect {
		width: calc(100% + 3px);
		height: 51px;
		background: linear-gradient(180deg, #ffffff 59%, #dfe4e8 100%);
		border-radius: 4px;
		border-top-right-radius: 0;
		border-bottom-right-radius: 0;
		border: none;
		box-shadow: inset 0px -1px 4px rgba(255, 255, 255, 0.1);
		-webkit-clip-path: inset(-2px 2px -2px -2px);
		clip-path: inset(-2px 2px -2px -2px);
	}

	.event-bg__right {
		position: absolute;
		top: 0;
		right: 0;
		z-index: 10;
		width: 22px;
		height: 53px;
		background: url('data:image/svg+xml,<svg width="22" height="53" viewBox="0 0 22 53" fill="none" xmlns="http://www.w3.org/2000/svg"><mask id="path-1-inside-1_127_5" fill="white"><path fill-rule="evenodd" clip-rule="evenodd" d="M0 53H18C20.2091 53 22 51.2091 22 49V17.3342C22 16.1697 21.4925 15.063 20.6101 14.3031L5.1252 0.968925C4.39927 0.343816 3.47309 0 2.5151 0H0V53Z" /></mask><path fill-rule="evenodd" clip-rule="evenodd" d="M0 53H18C20.2091 53 22 51.2091 22 49V17.3342C22 16.1697 21.4925 15.063 20.6101 14.3031L5.1252 0.968925C4.39927 0.343816 3.47309 0 2.5151 0H0V53Z" fill="url(%23paint0_linear_127_5)" /><path d="M0 53H-1V54H0V53ZM20.6101 14.3031L21.2626 13.5454L21.2626 13.5454L20.6101 14.3031ZM5.1252 0.968925L4.47268 1.72669L4.47268 1.72669L5.1252 0.968925ZM0 0V-1H-1V0H0ZM18 52H0V54H18V52ZM21 49C21 50.6569 19.6569 52 18 52V54C20.7614 54 23 51.7614 23 49H21ZM21 17.3342V49H23V17.3342H21ZM19.9576 15.0609C20.6194 15.6308 21 16.4608 21 17.3342H23C23 15.8786 22.3657 14.4952 21.2626 13.5454L19.9576 15.0609ZM4.47268 1.72669L19.9576 15.0609L21.2626 13.5454L5.77773 0.211156L4.47268 1.72669ZM2.5151 1C3.23359 1 3.92823 1.25786 4.47268 1.72669L5.77773 0.211156C4.87031 -0.570232 3.71258 -1 2.5151 -1V1ZM0 1H2.5151V-1H0V1ZM1 53V0H-1V53H1Z" fill="url(%23paint1_linear_127_5)" mask="url(%23path-1-inside-1_127_5)" /><defs><linearGradient id="paint0_linear_127_5" x1="-150.5" y1="0" x2="-150.5" y2="53" gradientUnits="userSpaceOnUse"><stop offset="0.586179" stop-color="white" /><stop offset="1" stop-color="%23DFE4E8" /></linearGradient><linearGradient id="paint1_linear_127_5" x1="-150.5" y1="0" x2="-150.5" y2="53" gradientUnits="userSpaceOnUse"><stop stop-color="white" /><stop offset="1" stop-color="white" /></linearGradient></defs></svg>');
	}
	.event__content {
		position: absolute;
		top: 0;
		left: 0;
		z-index: 30;
		width: 100%;
		height: 100%;
		padding: 0 15px;
		border-radius: 4px;

		display: flex;
		align-items: center;
		justify-content: space-between;
		font: $h4-medium;
		color: $text-dark;
	}
	.sport{
		min-width: 85px;
	}
    .league{
        font: $h5-regular;
    }
	.container-right {
		display: flex;
		align-items: center;
        width: 189px;
        justify-content: space-between;
	}
	.arrow {
		min-width: 10px;
	}
	.table-content {
		display: none;
		margin-top: 4px;
	}
	.table-visible {
		display: block;
	}



    .shadow-green {
		position: absolute;
		top: 0;
		left: 0;
		height: 53px;
		width: 100%;
		border-radius: 4px;
		z-index: 50;
		box-shadow: inset 0 -2px 2px 0 #8fd931;
		-webkit-clip-path: inset(32px 0 0 0);
		clip-path: inset(32px 0 0 0);
	}
	.shadow-blue {
		position: absolute;
		top: 0;
		left: 0;
		height: 53px;
		width: 100%;
		border-radius: 4px;
		z-index: 50;
		box-shadow: inset 0 -2px 2px 0 #24c1e5;
		-webkit-clip-path: inset(32px 0 0 0);
		clip-path: inset(32px 0 0 0);
	}
	.shadow-red {
		position: absolute;
		top: 0;
		left: 0;
		height: 53px;
		width: 100%;
		border-radius: 4px;
		z-index: 50;
		box-shadow: inset 0 -2px 2px 0 #d95c54;
		-webkit-clip-path: inset(32px 0 0 0);
		clip-path: inset(32px 0 0 0);
	}
	.shadow-yellow {
		position: absolute;
		top: 0;
		left: 0;
		height: 53px;
		width: 100%;
		border-radius: 4px;
		z-index: 50;
		box-shadow: inset 0 -2px 2px 0 #e69824;
		-webkit-clip-path: inset(32px 0 0 0);
		clip-path: inset(32px 0 0 0);
	}
	.shadow-purple {
		position: absolute;
		top: 0;
		left: 0;
		height: 53px;
		width: 100%;
		border-radius: 4px;
		z-index: 50;
		box-shadow: inset 0 -2px 2px 0 #962BEA;
		-webkit-clip-path: inset(32px 0 0 0);
		clip-path: inset(32px 0 0 0);
	}
	.shadow-gray {
		position: absolute;
		top: 0;
		left: 0;
		height: 53px;
		width: 100%;
		border-radius: 4px;
		z-index: 50;
		box-shadow: inset 0 -2px 2px 0 #F5AD22;
		-webkit-clip-path: inset(32px 0 0 0);
		clip-path: inset(32px 0 0 0);
	}
</style>
