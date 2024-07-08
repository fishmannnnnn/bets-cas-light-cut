<template>
	<div class="popup" ref="closePopupRef">
		<div class="top-container">
			<div class="popup__title">Coupon setting</div>
			<svg
				@click="emitClose"
				width="24"
				height="24"
				viewBox="0 0 24 24"
				fill="none"
				xmlns="http://www.w3.org/2000/svg">
				<path
					d="M18 6L6 18"
					stroke="#5E6471"
					stroke-width="1.5"
					stroke-linecap="round"
					stroke-linejoin="round" />
				<path
					d="M6 6L18 18"
					stroke="#5E6471"
					stroke-width="1.5"
					stroke-linecap="round"
					stroke-linejoin="round" />
			</svg>
		</div>
		<div class="radio-group">
			<template v-for="(item, index) in options">
				<label
					:class="[
						'radio-label',
						selectedRadioValue === item.id
							? 'radio-label-checked'
							: '',
					]">
					<input
						type="radio"
						:value="item.id"
						v-model="selectedRadioValue" />
					<span class="radio-title">{{ item.label }}</span>
				</label>
			</template>
		</div>
		<div class="bets">
			<div class="bets__title">Setting up quick bets</div>
			<div class="bets__description">
				Specify the bet size you use most often
			</div>
			<div class="bets__inputs">
				<input class="bets__input" value="2" />
				<input class="bets__input" value="5" />
				<input class="bets__input" value="10" />
			</div>
		</div>
		<div class="button-wrapper">
			<ButtonLarge text="Save" />
		</div>
	</div>
</template>

<script setup>
	import { ref } from 'vue';
	import { onClickOutside } from '@vueuse/core';
	import ButtonLarge from '../buttons/ButtonLarge.vue';
	const emit = defineEmits(['close']);
	const emitClose = () => {
		emit('close', false);
	};
	defineProps({
		data: Array,
	});
	const closePopupRef = ref(null);
	onClickOutside(closePopupRef, emitClose);

	const selectedRadioValue = ref('option-3');
	const options = [
		{
			id: 'option-1',
			label: 'Accept any odds changes',
		},
		{
			id: 'option-2',
			label: 'Accept only increased odds',
		},
		{
			id: 'option-3',
			label: 'Do not accept any odds changes',
		},
	];
</script>

<style lang="scss" scoped>
	@import '@/styles/global';
	.popup {
		z-index: 100000;
		padding: 30px 15px 30px;
		width: 100%;
		height: fit-content;
		box-shadow: inset 0 2px 4px 0 rgba(255, 255, 255, 0.32),
			0 -4px 20px 0 rgba(71, 212, 255, 0.42);
		background: $bg-white;
		border-radius: 12px;
		border-top: 1px solid $text-accent-blue;
		color: $text-dark;
	}

	.top-container {
		display: flex;
		justify-content: space-between;
	}
	.popup__title {
		font: $h3;
	}
	.container-right {
		display: flex;
		gap: 4px;
	}
	.radio-label {
		display: flex;
		gap: 8px;
		align-items: center;
		margin-bottom: 22px;
	}
	.radio-group {
		margin-top: 23px;
		font: $h5-regular;
	}
	.radio-label:last-child {
		margin-bottom: 0;
	}
	.bets {
		margin-top: 33px;
	}
	.bets__title {
		font: $h4-medium;
	}
	.bets__description {
		font: $h6-medium;
		color: $gray-text;
		margin-top: 6px;
	}
	.bets__inputs {
		margin-top: 12px;
		display: grid;
		grid-template-columns: 1fr 1fr 1fr;
		gap: 4px;
		font: $h5-regular;
		height: 48px;
	}
	.bets__input {
		border-radius: 4px;
		display: grid;
		place-items: center;
		background: $bg-white;
		box-shadow: 0 0 2px rgba(0, 0, 0, 0.25);
		border: none;
		width: 100%;
		height: 100%;
		text-align: center;
	}
	.button-wrapper {
		padding-top: 30px;
	}
</style>
