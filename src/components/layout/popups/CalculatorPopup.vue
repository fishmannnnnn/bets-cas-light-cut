<template>
	<div class="popup" ref="closePopupRef">
		<div class="top-container">
			<div class="popup__title">System calculator</div>
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
		<div class="select-container">
			<Select
				placeholder="2/3 - Options: 3"
				:modelValue="selectOption"
				:items="selectOptionList"
				@update:modelValue="selectOption = $event" />
		</div>
		<div class="bet">
			<div class="bet__title">Bet amount</div>
			<input class="bet__input" />
		</div>
		<div class="odds-table">
			<div class="titles">
				<div class="counter"></div>
				<div class="title">Odds</div>
				<div class="title">Winning</div>
				<div class="title">Losing</div>
				<div class="title">Return</div>
			</div>
			<div class="line" v-for="(item, index) in options">
				<div class="counter">{{ item.count }}</div>
				<input class="odds-input" v-model="item.odds" />
				<label
					:class="[
						'radio-label',
						item.radio == 'winning' ? 'radio-label-checked' : '',
					]">
					<input type="radio" value="winning" v-model="item.radio" />
					<span class="radio-title"></span>
				</label>
				<label
					:class="[
						'radio-label',
						item.radio == 'losing' ? 'radio-label-checked' : '',
					]">
					<input type="radio" value="losing" v-model="item.radio" />
					<span class="radio-title"></span>
				</label>
				<label
					:class="[
						'radio-label',
						item.radio == 'return' ? 'radio-label-checked' : '',
					]">
					<input type="radio" value="return" v-model="item.radio" />
					<span class="radio-title"></span>
				</label>
			</div>
		</div>
		<div class="winnings">
			<div class="amount">
				<div class="amount__title">Amount of one option</div>
				<div class="amount__cost">0.00 USDT</div>
			</div>
			<div class="possible">
				<div class="possible__title">Possible winnings</div>
				<div class="possible__cost">0.00 USDT</div>
			</div>
		</div>
		<div class="actions">
			<div class="reset">
				<ButtonSmall type="secondary" text="Reset" />
			</div>
			<div class="calculate"><ButtonSmall text="Calculate" /></div>
		</div>
	</div>
</template>

<script setup>
	import { ref, reactive } from 'vue';
	import { onClickOutside } from '@vueuse/core';
	import Select from '@/components/layout/inputs/Select.vue';
	import ButtonSmall from '../buttons/ButtonSmall.vue';
	const emit = defineEmits(['close']);
	const emitClose = () => {
		emit('close', false);
	};
	const closePopupRef = ref(null);
	onClickOutside(closePopupRef, emitClose);
	const selectOption = ref('');
	const selectOptionList = ['1/3', '2/3', '3/3'];

	const options = reactive([
		{
			count: 1,
			odds: '',
			radio: 'winning',
		},
		{
			count: 2,
			odds: '',
			radio: 'winning',
		},
		{
			count: 3,
			odds: '',
			radio: 'winning',
		},
	]);
</script>

<style lang="scss" scoped>
	@import '@/styles/global';
	.popup {
		z-index: 10000000;
		padding: 30px 15px 30px;
		width: 100%;
		height: fit-content;
		box-shadow: inset 0 2px 4px 0 rgba(255, 255, 255, 0.32),
			0 -4px 20px 0 rgba(71, 212, 255, 0.42);
		background: $bg-white;
		border-radius: 12px;
		border: 1px solid $text-accent-blue;
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
	.select-container {
		margin-top: 23px;
		height: 46px;
		width: 100%;
		position: relative;
		z-index: 9999;
	}
	.bet {
		display: flex;
		align-items: center;
		gap: 38px;
		margin-top: 15px;
	}
	.bet__title {
		font: $h4-medium;
		flex-shrink: 0;
	}
	.bet__input {
		height: 46px;
		background: $bg-white;
		box-shadow: 0 0 2px rgba(0, 0, 0, 0.25);
		border-radius: 4px;
		display: grid;
		place-items: center;
		border: none;
		width: 100%;
		text-align: center;
		font: $h5-regular;
	}
	.odds-input {
		height: 46px;
		background: $bg-white;
		box-shadow: 0 0 2px rgba(0, 0, 0, 0.25);
		border-radius: 4px;
		display: grid;
		place-items: center;
		border: none;
		min-width: 0;
		text-align: center;
		font: $h5-regular;
	}
	.counter {
		width: 9px;
		grid-row: 1 / span 2;
	}
	.odds-table {
		margin-top: 16px;
		padding: 20px 0 15px;
		border-top: 1px solid $separator;
		border-bottom: 1px solid $separator;
	}
	.titles {
		display: grid;
		grid-template-columns: 20px 1fr 1fr 1fr 1fr;
		margin-bottom: 16px;
		font: $h5-bold;
	}
	.title {
		display: grid;
		place-content: center;
	}
	.line {
		display: grid;
		grid-template-columns: 20px 1fr 1fr 1fr 1fr;
		font: $h4-medium;
		margin-bottom: 2px;
	}
	.counter,
	.odds-input,
	.radio-label {
		display: grid;
		place-content: center;
	}
	.line:last-child {
		margin-bottom: 0;
	}
	.winnings {
		margin-top: 20px;
	}
	.amount {
		display: flex;
		font: $h4-regular;
		justify-content: space-between;
	}
	.possible {
		font: $h4-medium;
		margin-top: 10px;
		color: $text-accent-blue;
		justify-content: space-between;
		display: flex;
	}
	.actions {
		padding-top: 20px;
		display: flex;
		gap: 8px;
	}
	.reset {
		flex-grow: 1;
	}
	.calculate {
		flex-grow: 1;
	}
	.radio-label {
		align-items: center;
	}
</style>
