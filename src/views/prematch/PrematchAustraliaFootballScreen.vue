gray
<template>
	<div class="page">
		<div class="header-container">
			<HeadUnregistered />
		</div>
		<div class="page-content">
			<div class="page-content__header">
				<div class="gradient-bg">
					<div class="gradient"></div>
				</div>
				<div class="header__tabs">
					<template v-for="item of tabList" :key="item.id">
						<div
							:class="[
								'tab',
								currentTab == item.id ? 'tab-active' : '',
							]"
							:id="item.id"
							@click="setCurrentTab($event)">
							{{ item.name }}
						</div>
					</template>
				</div>
				<div class="buttons">
					<svg
						width="18"
						height="19"
						viewBox="0 0 18 19"
						fill="none"
						xmlns="http://www.w3.org/2000/svg">
						<path
							d="M17.78 17.5008L14.6863 14.4761L14.6138 14.3659C14.479 14.2316 14.2947 14.156 14.1023 14.156C13.9098 14.156 13.7255 14.2316 13.5907 14.3659C10.9615 16.7779 6.91033 16.909 4.1238 14.6722C1.33728 12.4355 0.680102 8.52491 2.58812 5.53404C4.49613 2.54316 8.37726 1.40005 11.6576 2.86281C14.9379 4.32557 16.5994 7.94029 15.5403 11.3097C15.464 11.5531 15.5264 11.8178 15.7039 12.0041C15.8813 12.1904 16.147 12.27 16.4007 12.2129C16.6545 12.1557 16.8578 11.9706 16.9341 11.7272C18.2002 7.72866 16.288 3.42568 12.4345 1.60183C8.58104 -0.222012 3.94275 0.980624 1.52015 4.43176C-0.902457 7.88289 -0.382339 12.5468 2.74404 15.4064C5.87041 18.2661 10.6648 18.4632 14.0257 15.8703L16.7649 18.5483C17.0478 18.8237 17.5051 18.8237 17.788 18.5483C18.0707 18.2691 18.0707 17.8194 17.788 17.5401L17.78 17.5008Z"
							fill="gray" />
					</svg>
					<svg
						width="21"
						height="20"
						viewBox="0 0 21 20"
						fill="none"
						xmlns="http://www.w3.org/2000/svg">
						<path
							fill-rule="evenodd"
							clip-rule="evenodd"
							d="M8.80473 0.895828C9.079 0.344896 9.64238 0 10.255 0C10.8677 0 11.4311 0.344897 11.7053 0.895828L13.997 5.49918L19.1246 6.24231C19.7311 6.3302 20.2391 6.75267 20.4305 7.33804C20.6222 7.92414 20.4609 8.56601 20.0185 8.99334L16.3133 12.5716L17.1875 17.6252C17.2926 18.2331 17.0399 18.8448 16.5412 19.2041C16.0433 19.5627 15.3849 19.6095 14.8412 19.326L10.255 16.9346L5.66884 19.326C5.1252 19.6095 4.46677 19.5627 3.96893 19.2041C3.47014 18.8448 3.21747 18.2331 3.32262 17.6252L4.19677 12.5716L0.491627 8.99335C0.0491412 8.56601 -0.112092 7.92414 0.0795653 7.33804C0.270987 6.75267 0.779024 6.3302 1.3855 6.24231L6.51308 5.49918L8.80473 0.895828ZM10.255 1.51C10.2103 1.51 10.1732 1.53516 10.1565 1.56876L7.68861 6.52612C7.57824 6.74784 7.36614 6.90132 7.12102 6.93684L1.60208 7.7367C1.55814 7.74306 1.5261 7.77275 1.51478 7.80737C1.50369 7.84127 1.5122 7.87975 1.5406 7.90718L5.53336 11.7632C5.71327 11.937 5.79546 12.1885 5.75283 12.435L4.81053 17.8826C4.80453 17.9173 4.81829 17.955 4.85146 17.9789L4.41019 18.5915L4.85147 17.9789C4.88558 18.0034 4.93238 18.0071 4.97068 17.9871L9.90596 15.4137C10.1247 15.2996 10.3854 15.2996 10.6041 15.4137L15.5394 17.9871C15.5777 18.0071 15.6245 18.0034 15.6586 17.9789L15.9844 18.4311L15.6586 17.9789C15.6918 17.955 15.7056 17.9173 15.6996 17.8826L14.7573 12.435C14.7146 12.1885 14.7968 11.937 14.9767 11.7632L18.9695 7.90718C18.9979 7.87976 19.0064 7.84127 18.9953 7.80737C18.984 7.77275 18.9519 7.74306 18.908 7.7367L13.3891 6.93684C13.1439 6.90132 12.9318 6.74784 12.8215 6.52612L10.3536 1.56876C10.3369 1.53516 10.2998 1.51 10.255 1.51Z"
							fill="gray" />
					</svg>
					<svg
						width="5"
						height="19"
						viewBox="0 0 5 19"
						fill="none"
						xmlns="http://www.w3.org/2000/svg">
						<circle cx="2.51025" cy="2.75488" r="2" fill="gray" />
						<circle cx="2.51025" cy="9.75488" r="2" fill="gray" />
						<circle cx="2.51025" cy="16.7549" r="2" fill="gray" />
					</svg>
				</div>
			</div>
			<div class="content" v-if="currentTab == 'tab-1'">
				<div class="time-periods-container">
					<div class="time-periods">
						<div
							class="time-period"
							id="6h"
							@click="setActivePeriod($event)">
							<TimePeriod
								text="6 hours"
								:type="
									activePeriodItem == '6h'
										? 'active'
										: 'inactive'
								" />
						</div>
						<div
							class="time-period"
							id="12h"
							@click="setActivePeriod($event)">
							<TimePeriod
								text="12 hours"
								:type="
									activePeriodItem == '12h'
										? 'active'
										: 'inactive'
								" />
						</div>
						<div
							class="time-period"
							id="24h"
							@click="setActivePeriod($event)">
							<TimePeriod
								text="24 hours"
								:type="
									activePeriodItem == '24h'
										? 'active'
										: 'inactive'
								" />
						</div>
						<div
							class="time-period"
							id="3d"
							@click="setActivePeriod($event)">
							<TimePeriod
								text="3 days"
								:type="
									activePeriodItem == '3d'
										? 'active'
										: 'inactive'
								" />
						</div>
						<div
							class="time-period"
							id="all"
							@click="setActivePeriod($event)">
							<TimePeriod
								text="All"
								flag="all"
								:type="
									activePeriodItem == 'all'
										? 'active'
										: 'inactive'
								" />
						</div>
					</div>
				</div>
				<swiper-container
					id="sports-circles"
					mousewheel-force-to-axis="true"
					space-between="14px"
					slides-per-view="auto"
					free-mode="true">
					<swiper-slide>
						<div
							id="popular-circle"
							@click="setActiveCircle($event)">
							<CategoryCircle
								:isActive="
									activeCircle == 'popular-circle'
										? true
										: false
								"
								title="Popular"
								activeColor="yellow">
								<img
									class="item__circle"
									id="popular"
									src="@/assets/circles/popular.png" />
							</CategoryCircle>
						</div>
					</swiper-slide>
					<swiper-slide>
						<div
							id="football-circle"
							@click="setActiveCircle($event)">
							<CategoryCircle
								:isActive="
									activeCircle == 'football-circle'
										? true
										: false
								"
								title="Football"
								activeColor="green">
								<img
									class="item__circle"
									src="@/assets/circles/football.png" />
							</CategoryCircle>
						</div>
					</swiper-slide>
					<swiper-slide>
						<div
							id="basketball-circle"
							@click="setActiveCircle($event)">
							<CategoryCircle
								:isActive="
									activeCircle == 'basketball-circle'
										? true
										: false
								"
								title="Basketball"
								activeColor="brown">
								<img
									class="item__circle"
									src="@/assets/circles/basketball.png" />
							</CategoryCircle>
						</div>
					</swiper-slide>
					<swiper-slide>
						<div
							id="tennis-circle"
							@click="setActiveCircle($event)">
							<CategoryCircle
								:isActive="
									activeCircle == 'tennis-circle'
										? true
										: false
								"
								title="Tennis"
								activeColor="red">
								<img
									class="item__circle"
									src="@/assets/circles/tennis.png" />
							</CategoryCircle>
						</div>
					</swiper-slide>
					<swiper-slide>
						<div
							id="baseball-circle"
							@click="setActiveCircle($event)">
							<CategoryCircle
								:isActive="
									activeCircle == 'baseball-circle'
										? true
										: false
								"
								title="Baseball"
								activeColor="green">
								<img
									class="item__circle"
									src="@/assets/circles/baseball.png" />
							</CategoryCircle>
						</div>
					</swiper-slide>
					<swiper-slide>
						<div
							id="boxing-circle"
							@click="setActiveCircle($event)">
							<CategoryCircle
								:isActive="
									activeCircle == 'boxing-circle'
										? true
										: false
								"
								title="Boxing"
								activeColor="purple">
								<img
									class="item__circle"
									id="boxing"
									src="@/assets/circles/boxing.png" />
							</CategoryCircle>
						</div>
					</swiper-slide>
				</swiper-container>

				<div class="event-container">
					<ColoredEvent color="green">
						<img
							src="@/assets/events-icons/football.png"
							class="sport-img-football" />
						<div class="sport">Football</div>
					</ColoredEvent>
				</div>

				<div class="accordion">
					<div
						class="accordion-content"
						v-for="(item, index) in data">
						<div
							class="accordion-item"
							@click="setActiveAccordionItem($event)"
							:id="item.id">
							<div class="container-left">
								<img
									class="accordion-item__img"
									:src="getImageUrl(item.imgName)"
									alt="" />
								<div class="accordion-item__league">
									{{ item.league }}
								</div>
							</div>
							<svg
								:class="[
									activeAccordionItem === item.id
										? 'chevron-down'
										: '',
								]"
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
						<div
							class="accordion-item__tables"
							v-if="activeAccordionItem === item.id">
							<SportCategoryTable :data="item.tableData" />
							<SportCategoryTable :data="item.tableData" />
						</div>
					</div>
				</div>
			</div>
		</div>
		<div class="bottom-menu__wrapper">
			<BottomMenu />
		</div>
	</div>
</template>

<script setup>
	import { ref } from 'vue';
	import BottomMenu from '@/components/layout/menu/BottomMenu.vue';
	import HeadUnregistered from '@/components/layout/head/HeadUnregistered.vue';
	import TimePeriod from '@/components/layout/buttons/TimePeriod.vue';
	import SportCategoryTable from '@/components/layout/events/SportCategoryTable.vue';
	import ColoredEvent from '@/components/layout/events/ColoredEvent.vue';
	import CategoryCircle from '@/components/layout/events/CategoryCircle.vue';
	import { register } from 'swiper/element/bundle';
	register();

	const activePeriodItem = ref('all');
	const setActivePeriod = (event) => {
		activePeriodItem.value = event.currentTarget.id;
	};
	const activeCircle = ref('football-circle');
	const setActiveCircle = (event) => {
		activeCircle.value = event.currentTarget.id;
	};
	const activeAccordionItem = ref('001');
	const setActiveAccordionItem = (event) => {
		if (activeAccordionItem.value == event.currentTarget.id) {
			activeAccordionItem.value = '';
		} else {
			activeAccordionItem.value = event.currentTarget.id;
		}
	};
	const getImageUrl = (name) =>
		new URL(`/src/assets/events-icons/${name}.png`, import.meta.url).href;

	const currentTab = ref('tab-1');
	const setCurrentTab = (event) => {
		currentTab.value = event.currentTarget.id;
	};
	const tabList = [
		{ id: 'tab-1', name: 'Pre-match' },
		{ id: 'tab-2', name: 'Live' },
	];

	const data = [
		{
			id: '001',
			imgName: 'football',
			league: 'Australia Champions League B Australia Champions',
			tableData: {
				id: 12345,
				teams: ['Primer Unitet', 'Carlos Alcaraz'],
				date: 'Thurs. March 21 21:45',
				table: [
					[
						'W1',
						'X',
						'W2',
						'1X',
						'12',
						'X2',
						'H1',
						'H2',
						'More',
						'TU',
						'TO',
						'More',
						'All',
					],
					[
						'1',
						'1',
						'2.65',
						'3.5',
						'3.5',
						'3.5',
						'(+1.5) 1.85',
						'(+1.5) 1.85',
						'+17',
						'(1.5) 1.85',
						'(1.5) 1.85',
						'+17',
						'+217',
					],
				],
			},
		},
	];
</script>

<style lang="scss" scoped>
	@import '@/styles/global';
	.page {
		background: $bg-white;
		padding-bottom: 91px;
		min-height: 100dvh;
		height: 100%;
	}
	.page-content {
		position: relative;
		z-index: 2;
		margin-top: 15px;
	}
	.page-content__header {
		display: flex;
		justify-content: space-between;
		padding: 0 19px 0 7px;
		align-items: center;
		position: relative;
	}
	.header__tabs {
		display: flex;
	}
	.tab {
		font: $h5-medium;
		color: $text-dark;
		margin-left: 4px;
		padding: 10px 15px 12px;
	}
	.tab-active {
		color: $text-accent-blue;
		border: 1px solid rgb(180, 180, 180);
		border-bottom: none;
		border-radius: 6px 6px 0 0;
		background: white;
		position: relative;
		// box-shadow: 0 2px 0 rgba(47, 48, 53, 1);
	}
	.tab-active::before,
	.tab-active::after {
		position: absolute;
		bottom: 0px;
		width: 20px;
		height: 20px;
		content: ' ';
		border: 1px solid rgb(180, 180, 180);
	}
	.tab-active::before {
		left: -20px;
		border-bottom-right-radius: 12px;
		border-width: 0 1px 1px 0;
		box-shadow: 1px 9px 0 white;
	}
	.tab-active::after {
		right: -20px;
		border-bottom-left-radius: 12px;
		border-width: 0 0 1px 1px;
		box-shadow: -1px 9px 0 white;
	}
	.tab:first-of-type {
		margin-left: 0;
	}
	.buttons {
		display: flex;
		width: 100%;
		max-width: 81px;
		justify-content: space-between;
	}
	.gradient-bg {
		position: absolute;
		top: 38.5px;
		left: 0;
		width: 100%;
		height: 333px;
		border-top: 1px solid rgb(180, 180, 180);
		background: linear-gradient(180deg, white 0%, rgba(255,255,255,0) 100%);
		padding: 1px 0;
		z-index: -1;
	}
	.time-periods-container {
		padding: 20px 15px 0 15px;
		overflow-x: auto;
	}
	.time-periods {
		display: flex;
		gap: 4px;
		min-width: 341px;
	}
	#sports-circles {
		padding: 18px 15px 25px;
		display: flex;
		overflow-x: scroll;
		gap: 14px;
		swiper-slide {
			width: fit-content;
			max-width: 100%;
		}
	}
	#popular {
		width: 26px;
		height: 25px;
	}
	#boxing {
		width: 34px;
		height: 34px;
	}

	.event-container {
		padding: 0 15px;
	}
	.sport-img-football {
		width: 25px;
		height: 25px;
	}
	.sport-img {
		width: 25px;
		height: 25px;
	}
	.sport {
		height: fit-content;
		font: $h2;
	}
	.accordion {
		margin-top: 20px;
		display: flex;
		flex-direction: column;
		gap: 4px;
	}
	.accordion-item {
		margin: 0 15px;
		height: 44px;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.container-left {
		display: flex;
		align-items: center;
		gap: 8px;
	}
	.accordion-item__img {
		width: 24px;
		height: 24px;
		filter: drop-shadow( 0 0 2px rgba(0,0,0,0.25))
	}
	.chevron-up {
		transform: rotate(180deg);
	}
	.accordion-item__league {
		font: $h2;
		color: $text-dark;
		@media (max-width: 350px) {
			font: $h4-medium;
		}
	}
</style>
