<script setup>
	import BottomMenu from '@/components/layout/menu/BottomMenu.vue';
	import HeadUnregistered from '@/components/layout/head/HeadUnregistered.vue';
	import HeadRegistered from '@/components/layout/head/HeadRegistered.vue';
	import ButtonLarge from '@/components/layout/buttons/ButtonLarge.vue';
	import Search from '@/components/layout/inputs/Search.vue';
	import Event from '@/components/layout/events/Event.vue';
	import CategoryCircle from '@/components/layout/events/CategoryCircle.vue';
	import { register } from 'swiper/element/bundle';
	register();
</script>
<template>
	<div class="page">
		<div class="header-container">
			<HeadUnregistered />
		</div>
		<div class="gradient">
			<swiper-container
				id="carousel-wrapper"
				mousewheel-force-to-axis="true"
				space-between="4px"
				slides-per-view="auto"
				loop="true"
				free-mode="true">
				<swiper-slide>
					<img src="@/assets/images/image-carousel-1.png" />
				</swiper-slide>
				<swiper-slide>
					<img src="@/assets/images/image-carousel-2.png" />
				</swiper-slide>
				<swiper-slide>
					<img src="@/assets/images/image-carousel-1.png" />
				</swiper-slide>
				<swiper-slide>
					<img src="@/assets/images/image-carousel-2.png" />
				</swiper-slide>
			</swiper-container>
			<div class="button-promo">
				<ButtonLarge> </ButtonLarge>
			</div>
			<swiper-container
				id="categories-slider"
				mousewheel-force-to-axis="true"
				space-between="6px"
				slides-per-view="auto"
				free-mode="true">
				<swiper-slide>
					<div class="categories__item sport">
						<h2 class="categories__item-title">Sport</h2>
						<p class="categories__item-description">
							Top events for all sports
						</p>
					</div>
				</swiper-slide>
				<swiper-slide>
					<div class="categories__item live">
						<h2 class="categories__item-title">Live</h2>
						<p class="categories__item-description">
							Top events for all sports
						</p>
					</div>
				</swiper-slide>
				<swiper-slide>
					<div class="categories__item games">
						<img
							src="@/assets/images/games.png"
							class="games-img" />
						<h2 class="categories__item-title">Games 24/7</h2>
						<p class="categories__item-description">
							Top events for all sports
						</p>
					</div>
				</swiper-slide>
				<swiper-slide>
					<div class="categories__item casino">
						<img
							src="@/assets/images/games.png"
							class="games-img" />
						<h2 class="categories__item-title">Online Casino</h2>
						<p class="categories__item-description">
							Top events for all sports
						</p>
					</div>
				</swiper-slide>
			</swiper-container>
			<swiper-container
				id="sports-circles"
				mousewheel-force-to-axis="true"
				space-between="14px"
				slides-per-view="auto"
				free-mode="true">
				<swiper-slide>
					<CategoryCircle title="Live">
						<img
							class="item__circle"
							src="@/assets/circles/live.png" />
					</CategoryCircle>
				</swiper-slide>
				<swiper-slide>
					<CategoryCircle title="Football">
						<img
							class="item__circle"
							src="@/assets/circles/football.png" />
					</CategoryCircle>
				</swiper-slide>
				<swiper-slide>
					<CategoryCircle title="Basketball">
						<img
							class="item__circle"
							src="@/assets/circles/basketball.png" />
					</CategoryCircle>
				</swiper-slide>
				<swiper-slide>
					<CategoryCircle title="Tennis">
						<img
							class="item__circle"
							src="@/assets/circles/tennis.png" />
					</CategoryCircle>
				</swiper-slide>
				<swiper-slide>
					<CategoryCircle title="Baseball">
						<img
							class="item__circle"
							src="@/assets/circles/baseball.png" />
					</CategoryCircle>
				</swiper-slide>
				<swiper-slide>
					<CategoryCircle title="Boxing">
						<img
							class="item__circle"
							id="boxing"
							src="@/assets/circles/boxing.png" />
					</CategoryCircle>
				</swiper-slide>
			</swiper-container>

			<div class="input-search-events">
				<Search />
			</div>

			<div class="hot-events">
				<div class="hot-events__container-top">
					<h2 class="hot-events__title">Hot events</h2>
					<p class="hot-events__more">See all</p>
				</div>
				<div class="hot-events__wrapper">
					<Event
						:competitors="['Novak Djokovic', 'Carlos Alcaraz']"
						date="Thurs. March 21 21:45">
						<img src="@/assets/images/events/tennis.svg" alt="" />
					</Event>
				</div>
				<div class="hot-events__wrapper">
					<Event
						:competitors="['Oleksandr Usyk', 'Terence Crawford']"
						date="Thurs. March 21 21:45">
						<img src="@/assets/images/events/boxing.svg" alt="" />
					</Event>
				</div>
				<div class="hot-events__wrapper">
					<Event
						:competitors="['Golden State Warriors', 'Utah Jazz']"
						date="Thurs. March 21 21:45">
						<img
							src="@/assets/images/events/basketball.svg"
							alt="" />
					</Event>
				</div>
				<div class="hot-events__wrapper">
					<Event
						:competitors="[
							'Philadelphia Seventy sixers',
							'Chicago Bulls',
						]"
						date="Thurs. March 21 21:45">
						<img
							src="@/assets/images/events/basketball.svg"
							alt="" />
					</Event>
				</div>
				<div class="hot-events__wrapper">
					<Event
						:competitors="['Real Madrid', 'Manchester United']"
						date="Thurs. March 21 21:45">
						<img src="@/assets/images/events/football.svg" alt="" />
					</Event>
				</div>
				<div class="hot-events__wrapper">
					<Event
						:competitors="['Holger Rune', 'Hubert Hurkach']"
						date="Thurs. March 21 21:45">
						<img src="@/assets/images/events/tennis.svg" alt="" />
					</Event>
				</div>
				<div class="hot-events__wrapper"></div>
			</div>

			<div class="providers">
				<div class="providers__container-top">
					<h2 class="providers__title">Providers</h2>
					<p class="providers__more">See all</p>
				</div>
				<swiper-container
					id="providers-slider"
					mousewheel-force-to-axis="true"
					space-between="6px"
					slides-per-view="auto"
					free-mode="true">
					<swiper-slide>
						<div class="provider-item">
							<img
								src="@/assets/images/providers/spribe.png"
								class="provider-item__img" />
							<h5 class="provider-item__title">Spribe</h5>
						</div>
					</swiper-slide>
					<swiper-slide>
						<div class="provider-item">
							<img
								src="@/assets/images/providers/pragmatic.png"
								class="provider-item__img" />
							<h5 class="provider-item__title">Pragmatic</h5>
						</div>
					</swiper-slide>
					<swiper-slide>
						<div class="provider-item">
							<img
								src="@/assets/images/providers/inbet.png"
								class="provider-item__img" />
							<h5 class="provider-item__title">Inbet</h5>
						</div>
					</swiper-slide>
					<swiper-slide>
						<div class="provider-item">
							<img
								src="@/assets/images/providers/netent.png"
								class="provider-item__img" />
							<h5 class="provider-item__title">Netent</h5>
						</div>
					</swiper-slide>
					<swiper-slide>
						<div class="provider-item">
							<img
								src="@/assets/images/providers/amatic.png"
								class="provider-item__img" />
							<h5 class="provider-item__title">Amatic</h5>
						</div>
					</swiper-slide>
					<swiper-slide>
						<div class="provider-item">
							<img
								src="@/assets/images/providers/anbit.png"
								class="provider-item__img" />
							<h5 class="provider-item__title">Anbit</h5>
						</div>
					</swiper-slide>
				</swiper-container>
			</div>
		</div>

		<div class="second-gradient">
			<div class="input-game-search">
				<Search text="Quick game search" />
			</div>

			<div class="game-providers">
				<div class="game-provider">
					<div class="game-providers__container">
						<p class="game-providers__title">
							Game from <span>Spribe</span>
						</p>
						<p class="game-providers__more">See all</p>
					</div>
					<swiper-container
						id="spribe-games-slider"
						mousewheel-force-to-axis="true"
						space-between="4px"
						slides-per-view="auto"
						free-mode="true">
						<swiper-slide>
							<div class="game">
								<img
									src="@/assets/images/game-providers/spribe-poker.png" />
								<div class="game-name">Poker</div>
								<svg
									width="17"
									height="17"
									viewBox="0 0 17 17"
									fill="none"
									xmlns="http://www.w3.org/2000/svg">
									<path
										fill-rule="evenodd"
										clip-rule="evenodd"
										d="M8.5 1C8.75951 1 8.99652 1.15419 9.11139 1.39775L11.0597 5.52888L15.4168 6.19542C15.6735 6.23469 15.8867 6.42309 15.9667 6.68142C16.0468 6.93975 15.9798 7.22323 15.7939 7.41272L12.6417 10.6261L13.3856 15.1658C13.4295 15.4335 13.3243 15.7041 13.1144 15.8637C12.9044 16.0234 12.626 16.0444 12.3963 15.918L8.5 13.7734L4.60373 15.918C4.37401 16.0444 4.09563 16.0234 3.88565 15.8637C3.67566 15.7041 3.5705 15.4335 3.61437 15.1658L4.35829 10.6261L1.20611 7.41272C1.02024 7.22323 0.953231 6.93975 1.03326 6.68142C1.11329 6.42309 1.32648 6.23469 1.58323 6.19542L5.94028 5.52888L7.88861 1.39775C8.00348 1.15419 8.24049 1 8.5 1Z"
										fill="black"
										fill-opacity="0.39"
										stroke="#44B9EB"
										stroke-linecap="round"
										stroke-linejoin="round" />
								</svg>
							</div>
						</swiper-slide>
						<swiper-slide>
							<div class="game">
								<img
									src="@/assets/images/game-providers/spribe-aviator.png" />
								<div class="game-name">Aviator</div>
								<svg
									width="17"
									height="17"
									viewBox="0 0 17 17"
									fill="none"
									xmlns="http://www.w3.org/2000/svg">
									<path
										fill-rule="evenodd"
										clip-rule="evenodd"
										d="M8.5 1C8.75951 1 8.99652 1.15419 9.11139 1.39775L11.0597 5.52888L15.4168 6.19542C15.6735 6.23469 15.8867 6.42309 15.9667 6.68142C16.0468 6.93975 15.9798 7.22323 15.7939 7.41272L12.6417 10.6261L13.3856 15.1658C13.4295 15.4335 13.3243 15.7041 13.1144 15.8637C12.9044 16.0234 12.626 16.0444 12.3963 15.918L8.5 13.7734L4.60373 15.918C4.37401 16.0444 4.09563 16.0234 3.88565 15.8637C3.67566 15.7041 3.5705 15.4335 3.61437 15.1658L4.35829 10.6261L1.20611 7.41272C1.02024 7.22323 0.953231 6.93975 1.03326 6.68142C1.11329 6.42309 1.32648 6.23469 1.58323 6.19542L5.94028 5.52888L7.88861 1.39775C8.00348 1.15419 8.24049 1 8.5 1Z"
										fill="black"
										fill-opacity="0.39"
										stroke="#44B9EB"
										stroke-linecap="round"
										stroke-linejoin="round" />
								</svg>
							</div>
						</swiper-slide>
						<swiper-slide>
							<div class="game">
								<img
									src="@/assets/images/game-providers/spribe-mines.png" />
								<div class="game-name">Mines</div>
								<svg
									width="17"
									height="17"
									viewBox="0 0 17 17"
									fill="none"
									xmlns="http://www.w3.org/2000/svg">
									<path
										fill-rule="evenodd"
										clip-rule="evenodd"
										d="M8.5 1C8.75951 1 8.99652 1.15419 9.11139 1.39775L11.0597 5.52888L15.4168 6.19542C15.6735 6.23469 15.8867 6.42309 15.9667 6.68142C16.0468 6.93975 15.9798 7.22323 15.7939 7.41272L12.6417 10.6261L13.3856 15.1658C13.4295 15.4335 13.3243 15.7041 13.1144 15.8637C12.9044 16.0234 12.626 16.0444 12.3963 15.918L8.5 13.7734L4.60373 15.918C4.37401 16.0444 4.09563 16.0234 3.88565 15.8637C3.67566 15.7041 3.5705 15.4335 3.61437 15.1658L4.35829 10.6261L1.20611 7.41272C1.02024 7.22323 0.953231 6.93975 1.03326 6.68142C1.11329 6.42309 1.32648 6.23469 1.58323 6.19542L5.94028 5.52888L7.88861 1.39775C8.00348 1.15419 8.24049 1 8.5 1Z"
										fill="black"
										fill-opacity="0.39"
										stroke="#44B9EB"
										stroke-linecap="round"
										stroke-linejoin="round" />
								</svg>
							</div>
						</swiper-slide>
					</swiper-container>
				</div>
				<div class="game-provider">
					<div class="game-providers__container">
						<p class="game-providers__title">
							Game from <span>Pragmatic</span>
						</p>
						<p class="game-providers__more">See all</p>
					</div>
					<swiper-container
						id="pragmatic-games-slider"
						mousewheel-force-to-axis="true"
						space-between="4px"
						slides-per-view="auto"
						free-mode="true">
						<swiper-slide>
							<div class="game">
								<img
									src="@/assets/images/game-providers/pragmatic-dice.png"
									alt="" />
								<div class="game-name">Dice</div>
								<svg
									width="17"
									height="17"
									viewBox="0 0 17 17"
									fill="none"
									xmlns="http://www.w3.org/2000/svg">
									<path
										fill-rule="evenodd"
										clip-rule="evenodd"
										d="M8.5 1C8.75951 1 8.99652 1.15419 9.11139 1.39775L11.0597 5.52888L15.4168 6.19542C15.6735 6.23469 15.8867 6.42309 15.9667 6.68142C16.0468 6.93975 15.9798 7.22323 15.7939 7.41272L12.6417 10.6261L13.3856 15.1658C13.4295 15.4335 13.3243 15.7041 13.1144 15.8637C12.9044 16.0234 12.626 16.0444 12.3963 15.918L8.5 13.7734L4.60373 15.918C4.37401 16.0444 4.09563 16.0234 3.88565 15.8637C3.67566 15.7041 3.5705 15.4335 3.61437 15.1658L4.35829 10.6261L1.20611 7.41272C1.02024 7.22323 0.953231 6.93975 1.03326 6.68142C1.11329 6.42309 1.32648 6.23469 1.58323 6.19542L5.94028 5.52888L7.88861 1.39775C8.00348 1.15419 8.24049 1 8.5 1Z"
										fill="black"
										fill-opacity="0.39"
										stroke="#44B9EB"
										stroke-linecap="round"
										stroke-linejoin="round" />
								</svg>
							</div>
						</swiper-slide>
						<swiper-slide>
							<div class="game">
								<img
									src="@/assets/images/game-providers/pragmatic-mines.png"
									alt="" />
								<div class="game-name">Mines</div>
								<svg
									width="17"
									height="17"
									viewBox="0 0 17 17"
									fill="none"
									xmlns="http://www.w3.org/2000/svg">
									<path
										fill-rule="evenodd"
										clip-rule="evenodd"
										d="M8.5 1C8.75951 1 8.99652 1.15419 9.11139 1.39775L11.0597 5.52888L15.4168 6.19542C15.6735 6.23469 15.8867 6.42309 15.9667 6.68142C16.0468 6.93975 15.9798 7.22323 15.7939 7.41272L12.6417 10.6261L13.3856 15.1658C13.4295 15.4335 13.3243 15.7041 13.1144 15.8637C12.9044 16.0234 12.626 16.0444 12.3963 15.918L8.5 13.7734L4.60373 15.918C4.37401 16.0444 4.09563 16.0234 3.88565 15.8637C3.67566 15.7041 3.5705 15.4335 3.61437 15.1658L4.35829 10.6261L1.20611 7.41272C1.02024 7.22323 0.953231 6.93975 1.03326 6.68142C1.11329 6.42309 1.32648 6.23469 1.58323 6.19542L5.94028 5.52888L7.88861 1.39775C8.00348 1.15419 8.24049 1 8.5 1Z"
										fill="black"
										fill-opacity="0.39"
										stroke="#44B9EB"
										stroke-linecap="round"
										stroke-linejoin="round" />
								</svg>
							</div>
						</swiper-slide>
						<swiper-slide>
							<div class="game">
								<img
									src="@/assets/images/game-providers/pragmatic-roulette.png"
									alt="" />
								<div class="game-name">Mini Roulette</div>
								<svg
									width="17"
									height="17"
									viewBox="0 0 17 17"
									fill="none"
									xmlns="http://www.w3.org/2000/svg">
									<path
										fill-rule="evenodd"
										clip-rule="evenodd"
										d="M8.5 1C8.75951 1 8.99652 1.15419 9.11139 1.39775L11.0597 5.52888L15.4168 6.19542C15.6735 6.23469 15.8867 6.42309 15.9667 6.68142C16.0468 6.93975 15.9798 7.22323 15.7939 7.41272L12.6417 10.6261L13.3856 15.1658C13.4295 15.4335 13.3243 15.7041 13.1144 15.8637C12.9044 16.0234 12.626 16.0444 12.3963 15.918L8.5 13.7734L4.60373 15.918C4.37401 16.0444 4.09563 16.0234 3.88565 15.8637C3.67566 15.7041 3.5705 15.4335 3.61437 15.1658L4.35829 10.6261L1.20611 7.41272C1.02024 7.22323 0.953231 6.93975 1.03326 6.68142C1.11329 6.42309 1.32648 6.23469 1.58323 6.19542L5.94028 5.52888L7.88861 1.39775C8.00348 1.15419 8.24049 1 8.5 1Z"
										fill="black"
										fill-opacity="0.39"
										stroke="#44B9EB"
										stroke-linecap="round"
										stroke-linejoin="round" />
								</svg>
							</div>
						</swiper-slide>
					</swiper-container>
				</div>
				<div class="game-provider">
					<div class="game-providers__container">
						<p class="game-providers__title">
							Game from <span>Netent</span>
						</p>
						<p class="game-providers__more">See all</p>
					</div>
					<swiper-container
						id="netent-games-slider"
						mousewheel-force-to-axis="true"
						space-between="4px"
						slides-per-view="auto"
						free-mode="true">
						<swiper-slide>
							<div class="game">
								<img
									src="@/assets/images/game-providers/netent-hilo.png"
									alt="" />
								<div class="game-name">HiLo</div>
								<svg
									width="17"
									height="17"
									viewBox="0 0 17 17"
									fill="none"
									xmlns="http://www.w3.org/2000/svg">
									<path
										fill-rule="evenodd"
										clip-rule="evenodd"
										d="M8.5 1C8.75951 1 8.99652 1.15419 9.11139 1.39775L11.0597 5.52888L15.4168 6.19542C15.6735 6.23469 15.8867 6.42309 15.9667 6.68142C16.0468 6.93975 15.9798 7.22323 15.7939 7.41272L12.6417 10.6261L13.3856 15.1658C13.4295 15.4335 13.3243 15.7041 13.1144 15.8637C12.9044 16.0234 12.626 16.0444 12.3963 15.918L8.5 13.7734L4.60373 15.918C4.37401 16.0444 4.09563 16.0234 3.88565 15.8637C3.67566 15.7041 3.5705 15.4335 3.61437 15.1658L4.35829 10.6261L1.20611 7.41272C1.02024 7.22323 0.953231 6.93975 1.03326 6.68142C1.11329 6.42309 1.32648 6.23469 1.58323 6.19542L5.94028 5.52888L7.88861 1.39775C8.00348 1.15419 8.24049 1 8.5 1Z"
										fill="black"
										fill-opacity="0.39"
										stroke="#44B9EB"
										stroke-linecap="round"
										stroke-linejoin="round" />
								</svg>
							</div>
						</swiper-slide>
						<swiper-slide>
							<div class="game">
								<img
									src="@/assets/images/game-providers/netent-plinko.png"
									alt="" />
								<div class="game-name">Plinko</div>
								<svg
									width="17"
									height="17"
									viewBox="0 0 17 17"
									fill="none"
									xmlns="http://www.w3.org/2000/svg">
									<path
										fill-rule="evenodd"
										clip-rule="evenodd"
										d="M8.5 1C8.75951 1 8.99652 1.15419 9.11139 1.39775L11.0597 5.52888L15.4168 6.19542C15.6735 6.23469 15.8867 6.42309 15.9667 6.68142C16.0468 6.93975 15.9798 7.22323 15.7939 7.41272L12.6417 10.6261L13.3856 15.1658C13.4295 15.4335 13.3243 15.7041 13.1144 15.8637C12.9044 16.0234 12.626 16.0444 12.3963 15.918L8.5 13.7734L4.60373 15.918C4.37401 16.0444 4.09563 16.0234 3.88565 15.8637C3.67566 15.7041 3.5705 15.4335 3.61437 15.1658L4.35829 10.6261L1.20611 7.41272C1.02024 7.22323 0.953231 6.93975 1.03326 6.68142C1.11329 6.42309 1.32648 6.23469 1.58323 6.19542L5.94028 5.52888L7.88861 1.39775C8.00348 1.15419 8.24049 1 8.5 1Z"
										fill="black"
										fill-opacity="0.39"
										stroke="#44B9EB"
										stroke-linecap="round"
										stroke-linejoin="round" />
								</svg>
							</div>
						</swiper-slide>
						<swiper-slide>
							<div class="game">
								<img
									src="@/assets/images/game-providers/netent-goal.png"
									alt="" />
								<div class="game-name">Goal</div>
								<svg
									width="17"
									height="17"
									viewBox="0 0 17 17"
									fill="none"
									xmlns="http://www.w3.org/2000/svg">
									<path
										fill-rule="evenodd"
										clip-rule="evenodd"
										d="M8.5 1C8.75951 1 8.99652 1.15419 9.11139 1.39775L11.0597 5.52888L15.4168 6.19542C15.6735 6.23469 15.8867 6.42309 15.9667 6.68142C16.0468 6.93975 15.9798 7.22323 15.7939 7.41272L12.6417 10.6261L13.3856 15.1658C13.4295 15.4335 13.3243 15.7041 13.1144 15.8637C12.9044 16.0234 12.626 16.0444 12.3963 15.918L8.5 13.7734L4.60373 15.918C4.37401 16.0444 4.09563 16.0234 3.88565 15.8637C3.67566 15.7041 3.5705 15.4335 3.61437 15.1658L4.35829 10.6261L1.20611 7.41272C1.02024 7.22323 0.953231 6.93975 1.03326 6.68142C1.11329 6.42309 1.32648 6.23469 1.58323 6.19542L5.94028 5.52888L7.88861 1.39775C8.00348 1.15419 8.24049 1 8.5 1Z"
										fill="black"
										fill-opacity="0.39"
										stroke="#44B9EB"
										stroke-linecap="round"
										stroke-linejoin="round" />
								</svg>
							</div>
						</swiper-slide>
					</swiper-container>
				</div>
				<div class="game-provider">
					<div class="game-providers__container">
						<p class="game-providers__title">
							Game from <span>Amatic</span>
						</p>
						<p class="game-providers__more">See all</p>
					</div>
					<swiper-container
						id="amatic-games-slider"
						mousewheel-force-to-axis="true"
						space-between="4px"
						slides-per-view="auto"
						free-mode="true">
						<swiper-slide>
							<div class="game">
								<img
									src="@/assets/images/game-providers/netent-hilo.png"
									alt="" />
								<div class="game-name">HiLo</div>
								<svg
									width="17"
									height="17"
									viewBox="0 0 17 17"
									fill="none"
									xmlns="http://www.w3.org/2000/svg">
									<path
										fill-rule="evenodd"
										clip-rule="evenodd"
										d="M8.5 1C8.75951 1 8.99652 1.15419 9.11139 1.39775L11.0597 5.52888L15.4168 6.19542C15.6735 6.23469 15.8867 6.42309 15.9667 6.68142C16.0468 6.93975 15.9798 7.22323 15.7939 7.41272L12.6417 10.6261L13.3856 15.1658C13.4295 15.4335 13.3243 15.7041 13.1144 15.8637C12.9044 16.0234 12.626 16.0444 12.3963 15.918L8.5 13.7734L4.60373 15.918C4.37401 16.0444 4.09563 16.0234 3.88565 15.8637C3.67566 15.7041 3.5705 15.4335 3.61437 15.1658L4.35829 10.6261L1.20611 7.41272C1.02024 7.22323 0.953231 6.93975 1.03326 6.68142C1.11329 6.42309 1.32648 6.23469 1.58323 6.19542L5.94028 5.52888L7.88861 1.39775C8.00348 1.15419 8.24049 1 8.5 1Z"
										fill="black"
										fill-opacity="0.39"
										stroke="#44B9EB"
										stroke-linecap="round"
										stroke-linejoin="round" />
								</svg>
							</div>
						</swiper-slide>
						<swiper-slide>
							<div class="game">
								<img
									src="@/assets/images/game-providers/amatic-hilo.png"
									alt="" />
								<div class="game-name">HiLo</div>
								<svg
									width="17"
									height="17"
									viewBox="0 0 17 17"
									fill="none"
									xmlns="http://www.w3.org/2000/svg">
									<path
										fill-rule="evenodd"
										clip-rule="evenodd"
										d="M8.5 1C8.75951 1 8.99652 1.15419 9.11139 1.39775L11.0597 5.52888L15.4168 6.19542C15.6735 6.23469 15.8867 6.42309 15.9667 6.68142C16.0468 6.93975 15.9798 7.22323 15.7939 7.41272L12.6417 10.6261L13.3856 15.1658C13.4295 15.4335 13.3243 15.7041 13.1144 15.8637C12.9044 16.0234 12.626 16.0444 12.3963 15.918L8.5 13.7734L4.60373 15.918C4.37401 16.0444 4.09563 16.0234 3.88565 15.8637C3.67566 15.7041 3.5705 15.4335 3.61437 15.1658L4.35829 10.6261L1.20611 7.41272C1.02024 7.22323 0.953231 6.93975 1.03326 6.68142C1.11329 6.42309 1.32648 6.23469 1.58323 6.19542L5.94028 5.52888L7.88861 1.39775C8.00348 1.15419 8.24049 1 8.5 1Z"
										fill="black"
										fill-opacity="0.39"
										stroke="#44B9EB"
										stroke-linecap="round"
										stroke-linejoin="round" />
								</svg>
							</div>
						</swiper-slide>
						<swiper-slide>
							<div class="game">
								<img
									src="@/assets/images/game-providers/amatic-mines.png"
									alt="" />
								<div class="game-name">Mines</div>
								<svg
									width="17"
									height="17"
									viewBox="0 0 17 17"
									fill="none"
									xmlns="http://www.w3.org/2000/svg">
									<path
										fill-rule="evenodd"
										clip-rule="evenodd"
										d="M8.5 1C8.75951 1 8.99652 1.15419 9.11139 1.39775L11.0597 5.52888L15.4168 6.19542C15.6735 6.23469 15.8867 6.42309 15.9667 6.68142C16.0468 6.93975 15.9798 7.22323 15.7939 7.41272L12.6417 10.6261L13.3856 15.1658C13.4295 15.4335 13.3243 15.7041 13.1144 15.8637C12.9044 16.0234 12.626 16.0444 12.3963 15.918L8.5 13.7734L4.60373 15.918C4.37401 16.0444 4.09563 16.0234 3.88565 15.8637C3.67566 15.7041 3.5705 15.4335 3.61437 15.1658L4.35829 10.6261L1.20611 7.41272C1.02024 7.22323 0.953231 6.93975 1.03326 6.68142C1.11329 6.42309 1.32648 6.23469 1.58323 6.19542L5.94028 5.52888L7.88861 1.39775C8.00348 1.15419 8.24049 1 8.5 1Z"
										fill="black"
										fill-opacity="0.39"
										stroke="#44B9EB"
										stroke-linecap="round"
										stroke-linejoin="round" />
								</svg>
							</div>
						</swiper-slide>
					</swiper-container>
				</div>
				<div class="game-provider">
					<div class="game-providers__container">
						<p class="game-providers__title">
							Game from <span>Inbet</span>
						</p>
						<p class="game-providers__more">See all</p>
					</div>
					<swiper-container
						id="inbet-games-slider"
						mousewheel-force-to-axis="true"
						space-between="4px"
						slides-per-view="auto"
						free-mode="true">
						<swiper-slide>
							<div class="game">
								<img
									src="@/assets/images/game-providers/inbet-hotline.png"
									alt="" />
								<div class="game-name">HotLine</div>
								<svg
									width="17"
									height="17"
									viewBox="0 0 17 17"
									fill="none"
									xmlns="http://www.w3.org/2000/svg">
									<path
										fill-rule="evenodd"
										clip-rule="evenodd"
										d="M8.5 1C8.75951 1 8.99652 1.15419 9.11139 1.39775L11.0597 5.52888L15.4168 6.19542C15.6735 6.23469 15.8867 6.42309 15.9667 6.68142C16.0468 6.93975 15.9798 7.22323 15.7939 7.41272L12.6417 10.6261L13.3856 15.1658C13.4295 15.4335 13.3243 15.7041 13.1144 15.8637C12.9044 16.0234 12.626 16.0444 12.3963 15.918L8.5 13.7734L4.60373 15.918C4.37401 16.0444 4.09563 16.0234 3.88565 15.8637C3.67566 15.7041 3.5705 15.4335 3.61437 15.1658L4.35829 10.6261L1.20611 7.41272C1.02024 7.22323 0.953231 6.93975 1.03326 6.68142C1.11329 6.42309 1.32648 6.23469 1.58323 6.19542L5.94028 5.52888L7.88861 1.39775C8.00348 1.15419 8.24049 1 8.5 1Z"
										fill="black"
										fill-opacity="0.39"
										stroke="#44B9EB"
										stroke-linecap="round"
										stroke-linejoin="round" />
								</svg>
							</div>
						</swiper-slide>
						<swiper-slide>
							<div class="game">
								<img
									src="@/assets/images/game-providers/inbet-keno.png"
									alt="" />
								<div class="game-name">Keno</div>
								<svg
									width="17"
									height="17"
									viewBox="0 0 17 17"
									fill="none"
									xmlns="http://www.w3.org/2000/svg">
									<path
										fill-rule="evenodd"
										clip-rule="evenodd"
										d="M8.5 1C8.75951 1 8.99652 1.15419 9.11139 1.39775L11.0597 5.52888L15.4168 6.19542C15.6735 6.23469 15.8867 6.42309 15.9667 6.68142C16.0468 6.93975 15.9798 7.22323 15.7939 7.41272L12.6417 10.6261L13.3856 15.1658C13.4295 15.4335 13.3243 15.7041 13.1144 15.8637C12.9044 16.0234 12.626 16.0444 12.3963 15.918L8.5 13.7734L4.60373 15.918C4.37401 16.0444 4.09563 16.0234 3.88565 15.8637C3.67566 15.7041 3.5705 15.4335 3.61437 15.1658L4.35829 10.6261L1.20611 7.41272C1.02024 7.22323 0.953231 6.93975 1.03326 6.68142C1.11329 6.42309 1.32648 6.23469 1.58323 6.19542L5.94028 5.52888L7.88861 1.39775C8.00348 1.15419 8.24049 1 8.5 1Z"
										fill="black"
										fill-opacity="0.39"
										stroke="#44B9EB"
										stroke-linecap="round"
										stroke-linejoin="round" />
								</svg>
							</div>
						</swiper-slide>
						<swiper-slide>
							<div class="game">
								<img
									src="@/assets/images/game-providers/inbet-keno.png"
									alt="" />
								<div class="game-name">Keno</div>
								<svg
									width="17"
									height="17"
									viewBox="0 0 17 17"
									fill="none"
									xmlns="http://www.w3.org/2000/svg">
									<path
										fill-rule="evenodd"
										clip-rule="evenodd"
										d="M8.5 1C8.75951 1 8.99652 1.15419 9.11139 1.39775L11.0597 5.52888L15.4168 6.19542C15.6735 6.23469 15.8867 6.42309 15.9667 6.68142C16.0468 6.93975 15.9798 7.22323 15.7939 7.41272L12.6417 10.6261L13.3856 15.1658C13.4295 15.4335 13.3243 15.7041 13.1144 15.8637C12.9044 16.0234 12.626 16.0444 12.3963 15.918L8.5 13.7734L4.60373 15.918C4.37401 16.0444 4.09563 16.0234 3.88565 15.8637C3.67566 15.7041 3.5705 15.4335 3.61437 15.1658L4.35829 10.6261L1.20611 7.41272C1.02024 7.22323 0.953231 6.93975 1.03326 6.68142C1.11329 6.42309 1.32648 6.23469 1.58323 6.19542L5.94028 5.52888L7.88861 1.39775C8.00348 1.15419 8.24049 1 8.5 1Z"
										fill="black"
										fill-opacity="0.39"
										stroke="#44B9EB"
										stroke-linecap="round"
										stroke-linejoin="round" />
								</svg>
							</div>
						</swiper-slide>
					</swiper-container>
				</div>
			</div>
			<div class="button-support">
				<ButtonLarge text="Support 24/7" />
			</div>
			<p class="bottom-text">
				<span>18+</span> Lorem Ipsum is simply dummy text of the
				printing and typesetting industry. Lorem Ipsum has been the
				industry's standard dummy text ever since the 1500s, when an
				unknown printer took a galley of type and scrambled it to make a
				type specimen book. It has survived not only five centuries, but
				also the leap into electronic typesetting, remaining essentially
				unchanged.
			</p>
			<div class="bottom-menu__wrapper">
				<BottomMenu />
			</div>
		</div>
	</div>
</template>
<style lang="scss" scoped>
	@import '@/styles/global';
	.page {
		background: linear-gradient(180deg, #e8e8e8 0%, #f2f2f2 100%);
		padding-bottom: 71px;
	}
	.gradient {
		width: 100vw;
		// background: linear-gradient(180deg, #e8e8e8 0%, #f2f2f2 35.44%);
		overflow-x: hidden;
	}
	.second-gradient {
		overflow-x: hidden;
		margin-top: 25px;
		border-radius: 12px;
		background: linear-gradient(180deg, #ffffff 0%, #e8e8e8 100%);
		border-bottom-left-radius: 0;
		border-bottom-right-radius: 0;
	}
	.button-promo {
		margin-top: 16px;
		display: flex;
		padding: 0 15px 0;
	}
	#carousel-wrapper {
		padding: 13px 15px 0 16px;
		height: 140px;
		width: 100%;
		swiper-slide {
			width: 330px;
			max-width: 100%;
		}
		img {
			height: 100%;
			width: 100%;
			object-fit: cover;
			border-radius: 8px;
		}
	}
	#categories-slider {
		padding: 13px 15px 0 16px;
		height: 100%;
		width: 100%;
		swiper-slide {
			width: 140px;
			max-width: 100%;
		}
	}
	.categories__item {
		overflow: visible;
		margin-top: 15px;
		width: 140px;
		height: 141px;
		position: relative;
		background: url('data:image/svg+xml,<svg width="140" height="141" viewBox="0 0 140 141" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M8 0.579285H132C136.142 0.579285 139.5 3.93715 139.5 8.07928V118.862C139.5 120.859 138.703 122.774 137.287 124.182L123.988 137.399C122.582 138.795 120.682 139.579 118.701 139.579H8C3.85786 139.579 0.5 136.221 0.5 132.079V8.07928C0.5 3.93715 3.85786 0.579285 8 0.579285Z" fill="url(%23paint0_linear_126_2)" stroke="url(%23paint1_linear_126_2)" /><defs><linearGradient id="paint0_linear_126_2" x1="128" y1="135.35" x2="29.5625" y2="-7.40145" gradientUnits="userSpaceOnUse"><stop stop-color="%23419FD5" /><stop offset="0.586147" stop-color="%2382CBF4" /><stop offset="1" stop-color="%23C6F0FE" /></linearGradient><linearGradient id="paint1_linear_126_2" x1="130.5" y1="126.017" x2="44.7063" y2="-15.2469" gradientUnits="userSpaceOnUse"><stop offset="0.0742617" stop-color="%236DE9FA" /><stop offset="1" stop-color="%2364AACF" stop-opacity="0" /></linearGradient></defs></svg>');
		filter: drop-shadow(2px 4px 4px rgba(100, 210, 255, 0.3))
			drop-shadow(-2px -2px 4px rgba(0, 0, 0, 0.2));
	}
	.sport::before {
		content: '';
		position: absolute;
		background: url('@/assets/images/sport.svg');
		width: 78px;
		height: 78px;
		top: -12px;
		right: 9px;
		z-index: 8000;
	}
	.live::before {
		content: '';
		position: absolute;
		background: url('@/assets/images/live.png');
		width: 69px;
		height: 75px;
		top: -15px;
		right: 7px;
		z-index: 8000;
	}
	// .games::before {
	// 	content: '';
	// 	position: absolute;
	// 	// background: url('@/assets/images/games.png');
	// 	// display: block;
	// 	width: 101px;
	// 	height: 68px;
	// 	top: -14px;
	// 	right: 9px;
	// 	z-index: 8000;
	// }
	.games-img {
		position: absolute;
		top: -20px;
		right: -10px;
		width: 101px;
		height: auto;
	}
	// .casino::before {
	// 	content: '';
	// 	position: absolute;
	// 	background: url('@/assets/images/casino.svg');
	// 	width: 73px;
	// 	height: 88px;
	// 	top: -14px;
	// 	right: 9px;
	// 	z-index: 8000;
	// }
	.categories__item-title {
		font: $h2;
		padding-left: 8px;
		color: white;
		padding-top: 73px;
	}
	.categories__item-description {
		font: $h6-regular;
		color: white;
		padding: 4px 8px 0 8px;
	}
	#sports-circles {
		padding: 18px 15px 20px;
		swiper-slide {
			width: fit-content;
			max-width: 100%;
		}
	}
	.sports-circles__item {
		flex-shrink: 0;
		display: flex;
		flex-direction: column;
		gap: 2px;
		align-items: center;
	}
	.circle-bg {
		border-radius: 200px;
		width: 52px;
		height: 52px;
		background: linear-gradient(
			180deg,
			rgba(158, 165, 182, 1) 5%,
			rgba(64, 65, 71, 1) 55%,
			rgba(254, 180, 36, 1) 100%
		);
		box-shadow: 2px 2px 6px 0 rgba(255, 163, 79, 0.5);
		padding: 1px;
	}
	.circle {
		border-radius: 200px;
		width: 100%;
		height: 100%;
		background: linear-gradient(
			322deg,
			rgba(26, 27, 31, 1) 0%,
			rgba(101, 103, 111, 1) 100%
		);
		box-shadow: inset 0 3px 4px 0 rgba(255, 255, 255, 0.22);
		display: flex;
		align-items: center;
		justify-content: space-around;
	}
	.item__circle {
		width: 36px;
		height: 36px;
	}
	#boxing {
		width: 34px;
		height: 34px;
	}
	.sports-circles__item-title {
		font: normal 400 12px/120% 'Noto Sans', sans-serif;
		color: white;
	}

	.input-search-events {
		position: relative;
		z-index: 2;
		padding: 0 19px 0 11px;
	}

	.hot-events {
		margin: 30px 0 0 15px;
	}
	.hot-events__container-top {
		position: relative;
		z-index: 2;
		padding: 0 14px 0 22px;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.hot-events__title {
		font: $h2;
		color: $text-dark;
		position: relative;
		z-index: 2;
		&::before {
			content: url('@/assets/images/fire.svg');
			width: 25px;
			height: 25px;
			position: absolute;
			top: -9px;
			left: -28px;
		}
	}
	.hot-events__more {
		font: $h4-regular;
		color: #3399e2;
	}
	.hot-events__wrapper:nth-child(1) {
		margin-top: 12px;
	}
	.hot-events__wrapper {
		margin-top: 10px;
	}

	.hot-events__container {
		display: flex;
		min-width: 405px;
		gap: 6px;
	}

	.providers {
		margin-top: 30px;
		padding-left: 15px;
	}
	.providers__container-top {
		padding-right: 12px;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.providers__title {
		font: $h2;
		color: $text-dark;
	}
	.providers__more {
		font: $h4-regular;
		color: #3399E2;
	}
	#providers-slider {
		padding-top: 12px;
		swiper-slide {
			width: fit-content;
			max-width: 100%;
		}
	}
	.provider-item {
		display: flex;
		flex-direction: column;
		align-items: center;
		gap: 4px;
	}
	.provider-item__img {
		min-width: 60px;
		height: 60px;
	}
	.provider-item__title {
		color: $text-dark;
		font: $h5-regular;
	}
	.input-game-search {
		padding: 30px 15px 0;
	}

	.game-providers {
		margin-left: 15px;
	}
	.game-providers__container {
		margin-right: 12px;
		display: flex;
		align-items: center;
		justify-content: space-between;
		span {
			font: normal 700 18px/120% 'Inter', sans-serif;
			letter-spacing: 0.02em;
			background: $accent-blue-gradient;
			background-clip: text;
			-webkit-text-fill-color: transparent;
			-webkit-text-stroke: 0.5px #2991ba;
		}
	}
	.game-provider {
		margin-top: 20px;
	}
	.game-providers__title {
		font: $h2;
		color: $text-dark;
	}
	.game-providers__more {
		font: $h4-regular;
		color: #3399E2;
	}
	#spribe-games-slider,
	#pragmatic-games-slider,
	#netent-games-slider,
	#amatic-games-slider,
	#inbet-games-slider {
		padding-top: 12px;
		swiper-slide {
			width: fit-content;
			max-width: 100%;
		}
	}
	.game {
		border-radius: 4px;
		min-width: 133px;
		height: 90px;
		position: relative;
		img {
			border-radius: 4px;
		}
		svg {
			position: absolute;
			top: 4px;
			right: 4px;
		}
	}
	.game-name {
		position: absolute;
		bottom: 0;
		left: 0;
		width: 100%;
		font: normal 400 14px/120% 'Inter', sans-serif;
		padding: 6px 0 6px 9px;
		color: white;
		background: $secondary-button-bg;
		backdrop-filter: blur(5px);
	}
	.button-support {
		display: flex;
		margin-top: 30px;
		padding: 0 15px 0;
	}
	.bottom-text {
		padding: 20px 15px 12px;
		font: normal 400 13px/120% 'Noto Sans', sans-serif;
		color: #9ba0ab;
		span {
			font: normal 600 13px/120% 'Noto Sans', sans-serif;
			color: #44B9EB;
		}
	}
</style>
