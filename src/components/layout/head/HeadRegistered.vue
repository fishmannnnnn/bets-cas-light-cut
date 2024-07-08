<script setup>
	import Badge from "@/components/layout/badges/Badge.vue";
	import SideMenuRegistered from "../menu/SideMenuRegistered.vue";
	import { ref } from "vue";

	const showMenu = ref(false);
	const openMenu = () => {
		showMenu.value = true;
		document.body.classList.add("body-fixed");
		const bottomMenu = document.getElementsByClassName(
			"bottom-menu__wrapper"
		)[0];
		bottomMenu.classList.add("bottom-menu-inactive");
	};
	const handleClose = (newValue) => {
		showMenu.value = newValue;
		document.body.classList.remove("body-fixed");
		const bottomMenu = document.getElementsByClassName(
			"bottom-menu__wrapper"
		)[0];
		bottomMenu.classList.remove("bottom-menu-inactive");
	};
	const props = defineProps({
		counter: String,
		type: {
			type: String,
			default: "add",
		},
		className: String,
	});
</script>
<template>
	<header class="header-bg">
		<div class="bg__rect"></div>
		<div class="bg__right"></div>
		<div class="header__content">
			<div class="container-left">
				<svg
					class="menu"
					@click="openMenu"
					width="20"
					height="12"
					viewBox="0 0 20 12"
					fill="none"
					xmlns="http://www.w3.org/2000/svg">
					<rect width="20" height="2" rx="1" fill="#343434" />
					<rect y="5" width="20" height="2" rx="1" fill="#343434" />
					<rect y="10" width="20" height="2" rx="1" fill="#343434" />
				</svg>
				<img class="logo" src="@/components/icons/logo-light.svg" />
			</div>

			<div class="container-right">
				<img class="profile" src="@/components/icons/HeadProfile.svg" />
				<div class="info">
					<p class="info__id">ID 1234567</p>
					<p class="info__deposit">600 000.00 USD</p>
				</div>
				<button class="inbox">
					<div class="badge-container" v-if="counter != null">
						<Badge :count="counter ? counter : ``" />
					</div>
				</button>
				<button :class="type"></button>
			</div>
		</div>
	</header>
	<Transition name="slide">
		<div class="menu-container" v-if="showMenu">
			<SideMenuRegistered @close="handleClose" />
		</div>
	</Transition>
</template>
<style lang="scss" scoped>
	@media (max-width: 371px) {
		p.info__id {
			font-size: 11px;
		}
		p.info__deposit {
			font-size: 11px;
		}
	}
	@media (max-width: 350px) {
		p.info__id {
			font-size: 8px;
		}
		p.info__deposit {
			font-size: 8px;
		}
	}
	@import "@/styles/global";
	.menu-container {
		position: absolute;
		top: 0;
		left: 0;
		right: 0;
		height: 100dvh;
		width: 100vw;
	}
	.header-bg {
		border-radius: 4px;
		position: relative;
		filter: drop-shadow(0 2px 2px rgba(0, 0, 0, 0.2));
	}
	.bg__rect {
		height: 50px;
		width: calc(100% - 17px);
		background: white;
		border-radius: 4px;
		border-top-right-radius: 0;
		border-bottom-right-radius: 0;
		border: none;
	}
	.bg__right {
		background: url('data:image/svg+xml,<svg width="18" height="50" viewBox="0 0 18 50" fill="none" xmlns="http://www.w3.org/2000/svg"><path fill-rule="evenodd" clip-rule="evenodd" d="M0 50H0.110168C1.23212 50 2.30249 49.5288 3.06018 48.7014L16.95 33.533C17.6254 32.7954 18 31.8317 18 30.8316V4C18 1.79086 16.2091 0 14 0H0V50Z" fill="white"/></svg>');
		height: 50px;
		width: 18px;
		position: absolute;
		top: 0px;
		right: 0px;
	}
	.header__content {
		position: absolute;
		width: 100%;
		height: 100%;
		padding: 0px 14px 0 12px;
		top: 0px;
		left: 0px;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.container-left {
		display: flex;
		align-items: center;
		gap: 6px;
	}
	.container-right {
		display: flex;
		align-items: center;
		padding-left: 5px;
		flex-shrink: 0;
	}
	.menu {
		min-width: 20px;
	}
	.logo {
		min-width: 10px;
		min-height: 5px;
		width: 70%;
	}
	.profile {
		width: 25px;
		height: 26px;
	}
	.info {
		padding-left: 3px;
	}
	.info__id {
		font: $h7-regular;
		color: $gray-text;
	}
	.info__deposit {
		font: normal 700 12px/120% "Noto Sans", sans-serif;
		color: $text-accent-blue;
	}
	.inbox {
		position: relative;
		margin-left: 8px;
		min-width: 32px;
		height: 32px;
		border: none;
		filter: drop-shadow(0 0 1px rgba(0, 0, 0, 0.5));
		background: url('data:image/svg+xml,<svg width="32" height="32" viewBox="0 0 32 32" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M0 6C0 2.68629 2.68629 0 6 0H26C29.3137 0 32 2.68629 32 6V18.5961C32 20.1391 31.4055 21.6228 30.3401 22.7389L23.2727 30.1429C22.1406 31.3289 20.5723 32 18.9326 32H6C2.68629 32 0 29.3137 0 26V6Z" fill="%23F2F2F2"/><path d="M32 31V27.4142C32 26.5233 30.9229 26.0771 30.2929 26.7071L26.7071 30.2929C26.0771 30.9229 26.5233 32 27.4142 32H31C31.5523 32 32 31.5523 32 31Z" fill="%23F2F2F2"/><path d="M9.6 9H22.4C23.28 9 24 9.72 24 10.6V20.2C24 21.08 23.28 21.8 22.4 21.8H9.6C8.72 21.8 8 21.08 8 20.2V10.6C8 9.72 8.72 9 9.6 9Z" stroke="url(%23paint0_linear_3132_12500)" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/><path d="M24 10.6006L16 16.2006L8 10.6006" stroke="url(%23paint1_linear_3132_12500)" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/><defs><linearGradient id="paint0_linear_3132_12500" x1="17.2058" y1="21.8" x2="17.2058" y2="9" gradientUnits="userSpaceOnUse"><stop stop-color="%23248DB6"/><stop offset="1" stop-color="%237DD9FF"/></linearGradient><linearGradient id="paint1_linear_3132_12500" x1="17.2058" y1="16.2006" x2="17.2058" y2="10.6006" gradientUnits="userSpaceOnUse"><stop stop-color="%23248DB6"/><stop offset="1" stop-color="%237DD9FF"/></linearGradient></defs></svg>');
	}
	.badge-container {
		position: absolute;
		top: -7px;
		right: 0;
		transform: translateX(37%);
		z-index: 999;
	}
	.add {
		margin-left: 8px;
		min-width: 32px;
		height: 32px;
		border: none;
		background: url('data:image/svg+xml,<svg width="33" height="33" viewBox="0 0 33 33" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M6 0.5H26C29.0376 0.5 31.5 2.96243 31.5 6V18.5961C31.5 20.0105 30.9551 21.3705 29.9785 22.3937L22.9111 29.7976C21.8732 30.8849 20.4357 31.5 18.9326 31.5H6C2.96243 31.5 0.5 29.0376 0.5 26V6C0.5 2.96243 2.96243 0.5 6 0.5Z" fill="url(%23paint0_linear_3132_12506)" stroke="url(%23paint1_linear_3132_12506)"/><path d="M16 10V22" stroke="%23F2F2F2" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/><path d="M10 16H22" stroke="%23F2F2F2" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round"/><path d="M32 31V27.4142C32 26.5233 30.9229 26.0771 30.2929 26.7071L26.7071 30.2929C26.0771 30.9229 26.5233 32 27.4142 32H31C31.5523 32 32 31.5523 32 31Z" fill="url(%23paint2_linear_3132_12506)" stroke="url(%23paint3_linear_3132_12506)"/><defs><linearGradient id="paint0_linear_3132_12506" x1="18.4116" y1="32" x2="18.4116" y2="4.71616e-07" gradientUnits="userSpaceOnUse"><stop stop-color="%23248DB6"/><stop offset="1" stop-color="%237DD9FF"/></linearGradient><linearGradient id="paint1_linear_3132_12506" x1="18.9217" y1="27.7736" x2="18.9217" y2="4.22642" gradientUnits="userSpaceOnUse"><stop stop-color="%2324C1E5"/><stop offset="1" stop-color="%230C3992"/></linearGradient><linearGradient id="paint2_linear_3132_12506" x1="29.0275" y1="32" x2="29.0275" y2="25" gradientUnits="userSpaceOnUse"><stop stop-color="%23248DB6"/><stop offset="1" stop-color="%237DD9FF"/></linearGradient><linearGradient id="paint3_linear_3132_12506" x1="28.7739" y1="32" x2="29.3928" y2="25.0542" gradientUnits="userSpaceOnUse"><stop stop-color="%237AD7FC"/><stop offset="1" stop-color="%232991BA"/></linearGradient></defs></svg>');
		filter: drop-shadow(0 0 2px rgba(0, 0, 0, 0.25));
	}
	.add-disabled {
		margin-left: 8px;
		width: 32px;
		height: 32px;
		border: none;
		background: url('data:image/svg+xml,<svg width="33" height="33" viewBox="0 0 33 33" fill="none" xmlns="http://www.w3.org/2000/svg"><g opacity="0.5"><path d="M6 0.5H26C29.0376 0.5 31.5 2.96243 31.5 6V18.5961C31.5 20.0105 30.9551 21.3705 29.9785 22.3937L22.9111 29.7976C21.8732 30.8849 20.4357 31.5 18.9326 31.5H6C2.96243 31.5 0.5 29.0376 0.5 26V6C0.5 2.96243 2.96243 0.5 6 0.5Z" fill="url(%23paint0_linear_2072_12323)" stroke="url(%23paint1_linear_2072_12323)" /><path d="M16 10V22" stroke="%23080E13" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" /><path d="M10 16H22" stroke="%23080E13" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" /><path d="M32 31V27.4142C32 26.5233 30.9229 26.0771 30.2929 26.7071L26.7071 30.2929C26.0771 30.9229 26.5233 32 27.4142 32H31C31.5523 32 32 31.5523 32 31Z" fill="%23E6900D" stroke="%23F0BF0E" /></g><defs><linearGradient id="paint0_linear_2072_12323" x1="14.24" y1="29" x2="14.24" y2="2" gradientUnits="userSpaceOnUse"><stop stop-color="%23E68E0B" /><stop offset="1" stop-color="%23FFCE50" /></linearGradient><linearGradient id="paint1_linear_2072_12323" x1="16" y1="0" x2="16" y2="32" gradientUnits="userSpaceOnUse"><stop stop-color="%23FFDB58" /><stop offset="1" stop-color="%23EDBA02" /></linearGradient></defs></svg>');
		filter: drop-shadow(0 0 2px rgba(0, 0, 0, 0.59))
			drop-shadow(0 0 3px rgba(255, 163, 79, 0.71));
	}
</style>
