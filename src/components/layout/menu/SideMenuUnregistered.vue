<script setup>
	import { inject, ref } from 'vue';
	import Selector from '../inputs/Selector.vue';
	import ButtonMedium from '../buttons/ButtonMedium.vue';
	import { onClickOutside } from '@vueuse/core';

	const { selectedLanguage } = inject('selectedLanguage');
	const menuRef = ref(null);
	const emit = defineEmits(['close']);
	const emitClose = () => {
		emit('close', false);
	};
	onClickOutside(menuRef, emitClose);

	const getImageUrl = (name) =>
		new URL(`/src/assets/country-list/${name}.svg`, import.meta.url).href;

	const isAccordeonOpened = ref(true);
	const handleAccordeonClick = () => {
		isAccordeonOpened.value = !isAccordeonOpened.value;
	};
	const showSelectorPopup = ref(false);
	const handleClose = (newValue) => {
		showSelectorPopup.value = newValue;
	};

	const itemsList = [
		{
			flag: 'GB',
			language: 'English',
		},
		{
			flag: 'ES',
			language: 'Spanish',
		},
		{
			flag: 'FR',
			language: 'French',
		},
		{
			flag: 'TR',
			language: 'Turkish',
		},
		{
			flag: 'HT',
			language: 'Creole',
		},
		{
			flag: 'PT',
			language: 'Portuguese',
		},
		{
			flag: 'UA',
			language: 'Ukrainian',
		},
		{
			flag: 'RU',
			language: 'Russian',
		},
	];
</script>
<template>
	<div class="side-menu" ref="menuRef">
		<div :class="showSelectorPopup ? 'selector-bg' : ''">
			<Transition name="ontop" appear>
				<div class="language-selector" v-if="showSelectorPopup">
					<Selector
						title="Select a language"
						:itemsList="itemsList"
						@close="handleClose" />
				</div>
			</Transition>
		</div>

		<div class="side-menu__container">
			<div class="container-left">
				<svg
					class="menu-close"
					@click="emitClose"
					width="16"
					height="16"
					viewBox="0 0 16 16"
					fill="none"
					xmlns="http://www.w3.org/2000/svg">
					<rect
						x="16"
						y="1.45447"
						width="20.5704"
						height="2.05704"
						rx="1.02852"
						transform="rotate(135 16 1.45447)"
						fill="white" />
					<rect
						x="1.45459"
						width="20.5704"
						height="2.05704"
						rx="1.02852"
						transform="rotate(45 1.45459 0)"
						fill="white" />
				</svg>
				<svg
					class="side-menu__logo"
					width="117"
					height="16"
					viewBox="0 0 117 16"
					fill="none"
					xmlns="http://www.w3.org/2000/svg">
					<g clip-path="url(#clip0_4713_10070)">
						<path
							d="M31.6565 9.30597L32.5879 8.53766L33.0096 6.19812L32.3595 5.44672H27.6141L26.9111 9.30597H31.6565ZM31.0939 14.5996L32.1835 13.7116L32.5705 11.5602L31.8145 10.655H26.665L25.9447 14.5996H31.0939ZM26.2082 4.04669H33.2734L34.732 5.75425L34.1343 9.01586L33.1676 9.81826L34.2929 11.1504L33.6952 14.4289L31.7971 15.9999H24.0464L26.2082 4.04669Z"
							fill="white" />
						<path
							d="M42.5 10.9966L42.7461 9.6135L42.1134 8.8621H39.0025L38.0712 9.6135L37.8251 10.9966H42.5ZM35.5757 14.3095L36.5245 8.99895L38.3523 7.49615H42.9922L44.4508 9.22088L43.9059 12.2431H37.5967L37.2978 13.8825L37.9306 14.6339H41.0762L41.9728 13.8997L42.0783 13.319H43.7128L43.4842 14.5145L41.6916 15.9999H36.999L35.5757 14.3095Z"
							fill="white" />
						<path
							d="M46.5244 14.3095L47.5086 8.8621H45.9268L46.1728 7.49615H47.7897L48.2993 4.72991H49.8988L49.3889 7.49615H52.0954L51.8496 8.87927H49.1431L48.2468 13.8654L48.897 14.6168H50.8127L50.5666 15.9999H47.9657L46.5244 14.3095Z"
							fill="white" />
						<path
							d="M60.1277 9.30597L61.0591 8.53766L61.4808 6.19812L60.8307 5.44672H56.0853L55.3823 9.30597H60.1277ZM59.5651 14.5996L60.6547 13.7116L61.0417 11.5602L60.2857 10.655H55.1362L54.4159 14.5996H59.5651ZM54.6794 4.04669H61.7446L63.2032 5.75425L62.6055 9.01586L61.6388 9.81826L62.7641 11.1504L62.1664 14.4289L60.2683 15.9999H52.5176L54.6794 4.04669Z"
							fill="white" />
						<path
							d="M69.6004 14.6166L70.5321 13.8652L71.2878 9.63054L70.6373 8.87914H67.4737L66.5424 9.63054L65.7693 13.8652L66.4194 14.6166H69.6004ZM64.0469 14.3094L64.9956 8.99882L66.8235 7.49602H71.5336L72.9925 9.22075L72.0434 14.5313L70.2683 16H65.4881L64.0469 14.3094Z"
							fill="white" />
						<path
							d="M79.7411 14.6166L80.6727 13.8652L81.4284 9.63054L80.7779 8.87914H77.6143L76.683 9.63054L75.9099 13.8652L76.5601 14.6166H79.7411ZM74.1875 14.3094L75.1363 8.99882L76.9642 7.49602H81.6742L83.1331 9.22075L82.1841 14.5313L80.4089 16H75.6287L74.1875 14.3094Z"
							fill="white" />
						<path
							d="M84.0293 14.429L84.2226 13.4557H85.8398L85.7343 14.0872L86.2262 14.651H89.3194L90.0223 14.0872L90.2159 12.9606L89.7237 12.3627H85.9978L84.7325 10.8773L85.1015 8.84505L86.736 7.49602H91.0243L92.3951 9.08416L92.2018 10.0403H90.5672L90.6904 9.4086L90.1982 8.84505H87.3335L86.6305 9.4086L86.4372 10.4673L86.9291 11.0649H90.6377L91.9206 12.5846L91.5513 14.651L89.9171 16H85.3653L84.0293 14.429Z"
							fill="white" />
						<path
							d="M94.4341 14.3095L95.4182 8.8621H93.8364L94.0825 7.49615H95.6994L96.209 4.72991H97.8085L97.2986 7.49615H100.005L99.7593 8.87927H97.0528L96.1565 13.8654L96.8067 14.6168H98.7224L98.4763 15.9999H95.8753L94.4341 14.3095Z"
							fill="white" />
						<path
							d="M107.123 10.9966L107.369 9.6135L106.736 8.8621H103.625L102.694 9.6135L102.448 10.9966H107.123ZM100.198 14.3095L101.147 8.99895L102.975 7.49615H107.615L109.073 9.22088L108.528 12.2431H102.219L101.92 13.8825L102.553 14.6339H105.699L106.595 13.8997L106.701 13.319H108.335L108.107 14.5145L106.314 15.9999H101.622L100.198 14.3095Z"
							fill="white" />
						<path
							d="M111.586 7.49602H113.151L112.869 8.98165L114.662 7.49602H117L116.736 8.87939H114.82L112.641 10.6892L111.674 16H110.04L111.586 7.49602Z"
							fill="white" />
						<mask
							id="mask0_4713_10070"
							style="mask-type: luminance"
							maskUnits="userSpaceOnUse"
							x="11"
							y="12"
							width="8"
							height="5">
							<path
								d="M18.0267 12.2172L17.7174 13.9661L15.0824 16.2009H11.7275L14.3626 13.9661L14.6718 12.2172H18.0267Z"
								fill="white" />
						</mask>
						<g mask="url(#mask0_4713_10070)">
							<path
								d="M18.0267 12.2172L17.7174 13.9661L15.0824 16.2009H11.7275L14.3626 13.9661L14.6718 12.2172H18.0267Z"
								fill="url(#paint0_linear_4713_10070)" />
						</g>
						<mask
							id="mask1_4713_10070"
							style="mask-type: luminance"
							maskUnits="userSpaceOnUse"
							x="14"
							y="8"
							width="5"
							height="4">
							<path
								d="M18.518 9.42361L18.2009 11.2167H14.8487L15.1657 9.42361L14.251 8.29579H17.6032L18.518 9.42361Z"
								fill="white" />
						</mask>
						<g mask="url(#mask1_4713_10070)">
							<path
								d="M18.518 9.42361L18.2009 11.2167H14.8487L15.1657 9.42361L14.251 8.29579H17.6032L18.518 9.42361Z"
								fill="url(#paint1_linear_4713_10070)" />
						</g>
						<mask
							id="mask2_4713_10070"
							style="mask-type: luminance"
							maskUnits="userSpaceOnUse"
							x="14"
							y="4"
							width="5"
							height="4">
							<path
								d="M17.5046 7.29529L18.2842 6.62484L18.687 4.37181H15.3321L14.9293 6.62484L14.1523 7.29529H17.5046Z"
								fill="white" />
						</mask>
						<g mask="url(#mask2_4713_10070)">
							<path
								d="M17.5046 7.29529L18.2842 6.62484L18.687 4.37181H15.3321L14.9293 6.62484L14.1523 7.29529H17.5046Z"
								fill="url(#paint2_linear_4713_10070)" />
						</g>
						<mask
							id="mask3_4713_10070"
							style="mask-type: luminance"
							maskUnits="userSpaceOnUse"
							x="13"
							y="-1"
							width="7"
							height="5">
							<path
								d="M19.082 2.18125L18.8611 3.41821H15.5062L15.7271 2.18125L13.6846 -0.266673H17.0368L19.082 2.18125Z"
								fill="white" />
						</mask>
						<g mask="url(#mask3_4713_10070)">
							<path
								d="M19.082 2.18125L18.8611 3.41821H15.5062L15.7271 2.18125L13.6846 -0.266673H17.0368L19.082 2.18125Z"
								fill="url(#paint3_linear_4713_10070)" />
						</g>
						<mask
							id="mask4_4713_10070"
							style="mask-type: luminance"
							maskUnits="userSpaceOnUse"
							x="1"
							y="4"
							width="14"
							height="4">
							<path
								d="M13.1492 7.29529L13.9288 6.62484L14.3316 4.37181H2.07898L1.56445 7.29529H13.1492Z"
								fill="white" />
						</mask>
						<g mask="url(#mask4_4713_10070)">
							<path
								d="M13.1492 7.29529L13.9288 6.62484L14.3316 4.37181H2.07898L1.56445 7.29529H13.1492Z"
								fill="url(#paint4_linear_4713_10070)" />
						</g>
						<mask
							id="mask5_4713_10070"
							style="mask-type: luminance"
							maskUnits="userSpaceOnUse"
							x="0"
							y="12"
							width="14"
							height="5">
							<path
								d="M13.6715 12.2172L13.3623 13.9661L10.7272 16.2009H0L0.699037 12.2172H13.6715Z"
								fill="white" />
						</mask>
						<g mask="url(#mask5_4713_10070)">
							<path
								d="M13.6715 12.2172L13.3623 13.9661L10.7272 16.2009H0L0.699037 12.2172H13.6715Z"
								fill="url(#paint5_linear_4713_10070)" />
						</g>
						<mask
							id="mask6_4713_10070"
							style="mask-type: luminance"
							maskUnits="userSpaceOnUse"
							x="0"
							y="8"
							width="15"
							height="4">
							<path
								d="M14.1629 9.42361L13.8458 11.2167H0.875977L1.38791 8.29579H13.2481L14.1629 9.42361Z"
								fill="white" />
						</mask>
						<g mask="url(#mask6_4713_10070)">
							<path
								d="M14.1629 9.42361L13.8458 11.2167H0.875977L1.38791 8.29579H13.2481L14.1629 9.42361Z"
								fill="url(#paint6_linear_4713_10070)" />
						</g>
						<mask
							id="mask7_4713_10070"
							style="mask-type: luminance"
							maskUnits="userSpaceOnUse"
							x="2"
							y="-1"
							width="13"
							height="5">
							<path
								d="M14.7264 2.18125L14.5055 3.41821H2.24512L2.89218 -0.266673H12.6813L14.7264 2.18125Z"
								fill="white" />
						</mask>
						<g mask="url(#mask7_4713_10070)">
							<path
								d="M14.7264 2.18125L14.5055 3.41821H2.24512L2.89218 -0.266673H12.6813L14.7264 2.18125Z"
								fill="url(#paint7_linear_4713_10070)" />
						</g>
					</g>
					<defs>
						<linearGradient
							id="paint0_linear_4713_10070"
							x1="14.3308"
							y1="18.065"
							x2="16.8009"
							y2="0.629383"
							gradientUnits="userSpaceOnUse">
							<stop stop-color="#252ED6" />
							<stop offset="0.877278" stop-color="#00FC77" />
							<stop offset="1" stop-color="#00FC77" />
						</linearGradient>
						<linearGradient
							id="paint1_linear_4713_10070"
							x1="15.3163"
							y1="16.3998"
							x2="17.2814"
							y2="2.52844"
							gradientUnits="userSpaceOnUse">
							<stop stop-color="#252ED6" />
							<stop offset="0.877278" stop-color="#00FC77" />
							<stop offset="1" stop-color="#00FC77" />
						</linearGradient>
						<linearGradient
							id="paint2_linear_4713_10070"
							x1="14.8809"
							y1="16.6951"
							x2="17.0345"
							y2="1.49334"
							gradientUnits="userSpaceOnUse">
							<stop stop-color="#252ED6" />
							<stop offset="0.877278" stop-color="#00FC77" />
							<stop offset="1" stop-color="#00FC77" />
						</linearGradient>
						<linearGradient
							id="paint3_linear_4713_10070"
							x1="13.967"
							y1="18.0135"
							x2="16.437"
							y2="0.577774"
							gradientUnits="userSpaceOnUse">
							<stop stop-color="#252ED6" />
							<stop offset="0.877278" stop-color="#00FC77" />
							<stop offset="1" stop-color="#00FC77" />
						</linearGradient>
						<linearGradient
							id="paint4_linear_4713_10070"
							x1="6.50136"
							y1="16.0454"
							x2="8.72923"
							y2="0.319265"
							gradientUnits="userSpaceOnUse">
							<stop stop-color="#252ED6" />
							<stop offset="0.877278" stop-color="#00FC77" />
							<stop offset="1" stop-color="#00FC77" />
						</linearGradient>
						<linearGradient
							id="paint5_linear_4713_10070"
							x1="6.44259"
							y1="16.9843"
							x2="8.91264"
							y2="-0.451327"
							gradientUnits="userSpaceOnUse">
							<stop stop-color="#252ED6" />
							<stop offset="0.877278" stop-color="#00FC77" />
							<stop offset="1" stop-color="#00FC77" />
						</linearGradient>
						<linearGradient
							id="paint6_linear_4713_10070"
							x1="6.7368"
							y1="15.8446"
							x2="8.82644"
							y2="1.09419"
							gradientUnits="userSpaceOnUse">
							<stop stop-color="#252ED6" />
							<stop offset="0.877278" stop-color="#00FC77" />
							<stop offset="1" stop-color="#00FC77" />
						</linearGradient>
						<linearGradient
							id="paint7_linear_4713_10070"
							x1="6.47562"
							y1="16.9891"
							x2="8.94568"
							y2="-0.446658"
							gradientUnits="userSpaceOnUse">
							<stop stop-color="#252ED6" />
							<stop offset="0.877278" stop-color="#00FC77" />
							<stop offset="1" stop-color="#00FC77" />
						</linearGradient>
						<clipPath id="clip0_4713_10070">
							<rect
								width="117"
								height="16"
								fill="white"
								transform="matrix(1 0 0 -1 0 16)" />
						</clipPath>
					</defs>
				</svg>
			</div>
			<div class="side-menu__region" @click="showSelectorPopup = true">
				<!-- <img :src="getImageUrl(selectedLanguage)" /> -->
				<div class="selected-lang">{{ selectedLanguage }}</div>
			</div>
		</div>
		<nav class="side-menu__nav">
			<ul class="nav__list">
				<li class="list__item item-home">
					<h2 class="nav__title">Home</h2>
				</li>
				<li class="list__item item-live">
					<h2 class="nav__title">Live</h2>
				</li>
				<li class="list__item item-prematch">
					<h2 class="nav__title">Pre-match</h2>
				</li>
				<li class="list__item item-games">
					<h2 class="nav__title">Games</h2>
				</li>
				<li class="list__item item-results">
					<h2 class="nav__title">Results</h2>
				</li>
				<li class="list__item item-support">
					<h2 class="nav__title">Support</h2>
				</li>
				<li
					:class="[
						'list__item',
						'item-info',
						isAccordeonOpened ? 'item-opened' : 'item-closed',
					]"
					@click="handleAccordeonClick">
					<div class="item-info__container">
						<h2
							:class="[
								'nav__title',
								isAccordeonOpened ? 'active' : '',
							]">
							Info
						</h2>
						<svg
							v-if="isAccordeonOpened"
							width="12"
							height="7"
							viewBox="0 0 12 7"
							fill="none"
							xmlns="http://www.w3.org/2000/svg">
							<path
								d="M1 6L6 1L11 6"
								stroke="white"
								stroke-width="1.5"
								stroke-linecap="round"
								stroke-linejoin="round" />
						</svg>
						<svg
							v-else
							width="12"
							height="7"
							viewBox="0 0 12 7"
							fill="none"
							xmlns="http://www.w3.org/2000/svg"
							version="1.1"
							xmlns:xlink="http://www.w3.org/1999/xlink"
							transform="matrix(1,0,0,-1,0,0)">
							<path
								d="M1 6L6 1L11 6"
								stroke="white"
								stroke-width="1.5"
								stroke-linecap="round"
								stroke-linejoin="round"></path>
						</svg>
					</div>
					<ul class="item-info__list" v-if="isAccordeonOpened">
						<li>
							<h4>About us</h4>
						</li>
						<li>
							<h4>Affiliate program</h4>
						</li>
						<li>
							<h4>Rules</h4>
						</li>
						<li>
							<h4>Terms of Use</h4>
						</li>
					</ul>
				</li>
			</ul>
		</nav>

		<div class="profile-bottom__container">
			<ButtonMedium type="secondary">
				<svg
					width="18"
					height="19"
					viewBox="0 0 18 19"
					fill="none"
					xmlns="http://www.w3.org/2000/svg">
					<path
						fill-rule="evenodd"
						clip-rule="evenodd"
						d="M6.09269 4.63469C6.09269 3.00292 7.40101 1.69238 8.99983 1.69238C10.5987 1.69238 11.907 3.00292 11.907 4.63469C11.907 6.26647 10.5987 7.577 8.99983 7.577C7.40101 7.577 6.09269 6.26647 6.09269 4.63469ZM8.99983 0.192383C6.55908 0.192383 4.59269 2.18805 4.59269 4.63469C4.59269 7.08133 6.55908 9.077 8.99983 9.077C11.4406 9.077 13.407 7.08133 13.407 4.63469C13.407 2.18805 11.4406 0.192383 8.99983 0.192383ZM5.34269 11.2695C4.17151 11.2695 3.04977 11.7393 2.22384 12.5732C1.39814 13.4068 0.935547 14.536 0.935547 15.7118V17.558C0.935547 17.9722 1.27133 18.308 1.68555 18.308C2.09976 18.308 2.43555 17.9722 2.43555 17.558V15.7118C2.43555 14.9292 2.74356 14.18 3.28956 13.6288C3.83532 13.0778 4.574 12.7695 5.34269 12.7695H12.657C13.4257 12.7695 14.1643 13.0778 14.7101 13.6288C15.2561 14.18 15.5641 14.9292 15.5641 15.7118V17.558C15.5641 17.9722 15.8999 18.308 16.3141 18.308C16.7283 18.308 17.0641 17.9722 17.0641 17.558V15.7118C17.0641 14.536 16.6015 13.4068 15.7758 12.5732C14.9499 11.7393 13.8282 11.2695 12.657 11.2695H5.34269Z"
						fill="#2991BA" />
				</svg>
			</ButtonMedium>
			<ButtonMedium>GO!</ButtonMedium>
		</div>
	</div>
</template>

<style lang="scss" scoped>
	@import '@/styles/global';
	.selected-lang {
		font: $h4-medium;
		position: relative;
		color: white;
	}
	.selector-bg {
		position: absolute;
		top: 0;
		left: 0;
		height: 100dvh;
		width: 100vw;
		background: rgba(0, 0, 0, 0.6);
		backdrop-filter: blur(9px);
		z-index: 10000;
	}
	.language-selector {
		position: absolute;
		top: 0;
		left: 0;
		height: 100dvh;
		width: 100vw;
	}
	.side-menu {
		width: 89%;
		min-width: 280px;
		height: 100dvh;
		padding: 38px 20px 0 20px;
		position: fixed;
		top: 0;
		left: 0;
		z-index: 1;
		background: rgba(65, 64, 64, 0.6);
		backdrop-filter: blur(15px);
	}
	.menu-close {
		margin-left: 11px;
	}
	.side-menu__container {
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.container-left {
		display: flex;
		align-items: center;
	}
	.side-menu__logo {
		width: 117px;
		height: 16px;
		margin-left: 21px;
	}
	.side-menu__region {
		background: url('@/assets/side-menu/region-bg.svg');
		width: 32px;
		height: 26px;
		padding: 4px;
		display: flex;
		flex-direction: column;
		align-items: center;
		img {
			width: 22px;
			height: 16px;
			margin: 0 auto;
		}
	}
	.button-deposit {
		margin-top: 23px;
	}
	.side-menu__nav {
		padding: 31px 7px 50px 46px;
		height: calc(100% - 180px);
		touch-action: none;
		-webkit-overflow-scrolling: none;
		overflow: hidden;
		overscroll-behavior: none;
		overflow-y: scroll;
	}
	.nav__list {
		list-style-type: none;
		padding: 0;
	}
	.list__item {
		margin-top: 34px;
		&:nth-child(1) {
			margin-top: 0;
		}
	}

	.nav__title {
		font: $h2;
		color: white;
	}
	.item-home {
		position: relative;
	}
	.item-home::before {
		content: '';
		position: absolute;
		top: -7px;
		left: -46px;
		height: 38px;
		width: 38px;
		background: url('@/assets/side-menu/home.svg');
		z-index: 1;
		filter: drop-shadow(2px 2px 3px rgba(36, 141, 182, 0.6));
	}
	.item-live {
		position: relative;
	}
	.item-live::before {
		content: '';
		position: absolute;
		top: -7px;
		left: -46px;
		height: 38px;
		width: 38px;
		background: url('@/assets/side-menu/live.svg');
		z-index: 1000;
		filter: drop-shadow(2px 2px 3px rgba(36, 141, 182, 0.6));
	}
	.item-prematch {
		position: relative;
	}
	.item-prematch::before {
		content: '';
		position: absolute;
		top: -7px;
		left: -46px;
		height: 38px;
		width: 38px;
		background: url('@/assets/side-menu/prematch.svg');
		z-index: 1;
		filter: drop-shadow(2px 2px 3px rgba(36, 141, 182, 0.6));
	}
	.item-games {
		position: relative;
	}
	.item-games::before {
		content: '';
		position: absolute;
		top: -7px;
		left: -46px;
		height: 38px;
		width: 38px;
		background: url('@/assets/side-menu/games.svg');
		z-index: 1;
		filter: drop-shadow(2px 2px 3px rgba(36, 141, 182, 0.6));
	}
	.item-results {
		position: relative;
	}
	.item-results::before {
		content: '';
		position: absolute;
		top: -7px;
		left: -46px;
		height: 38px;
		width: 38px;
		background: url('@/assets/side-menu/results.svg');
		z-index: 1;
		filter: drop-shadow(2px 2px 3px rgba(36, 141, 182, 0.6));
	}
	.item-support {
		position: relative;
	}
	.item-support::before {
		content: '';
		position: absolute;
		top: -7px;
		left: -46px;
		height: 38px;
		width: 38px;
		background: url('@/assets/side-menu/support.svg');
		z-index: 1;
		filter: drop-shadow(2px 2px 3px rgba(36, 141, 182, 0.6));
	}
	.item-info__container {
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.active {
		color: $text-accent-blue;
	}
	.item-info {
		position: relative;
	}
	.item-info::before {
		content: '';
		position: absolute;
		top: -7px;
		left: -46px;
		height: 38px;
		width: 38px;
		background: url('@/assets/side-menu/info.svg');
		z-index: 1;
		filter: drop-shadow(2px 2px 3px rgba(36, 141, 182, 0.6));
	}
	.item-info__list {
		padding: 0;
		list-style-type: none;
		li {
			margin-top: 12px;
		}
		h4 {
			color: white;
			font: $h4-regular;
		}
	}
	.profile-bottom__container {
		width: calc(100% - 40px);
		position: absolute;
		bottom: 42px;
		left: 20px;
		display: flex;
		flex-direction: column;
		gap: 12px;
		align-items: center;
		z-index: 5;
	}
</style>
