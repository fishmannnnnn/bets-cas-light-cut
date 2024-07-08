<template>
	<div :class="'tab-bg-' + type">
		<div :class="['tab-' + type, flag == 'all' ? 'all' : '']">
			<div>{{ text }}</div>
		</div>
	</div>
</template>

<script setup>
	defineProps({
		type: { type: String, default: "inactive" },
		text: String,
		flag: String
	});
</script>

<style lang="scss" scoped>
	@import "@/styles/global";

	.tab-bg-active {
		background: $text-blue-stroke;
		padding: 1px;
		min-width: 48px;
		height: 30px;
		border-radius: 4px;
	}
	.tab-active {
		background: $accent-blue-gradient;
		border-radius: 4px;
		width: 100%;
		height: 100%;
		color: white;
		font: $h6-medium;
		padding: 6px 9px;
        text-align: center;
	}
	.tab-active .all {
		padding: 7px 16px;
		padding: 7px 10px;
		font: $h6-medium;
		display: flex;
		justify-content: space-around;
	}
	.tab-bg-inactive {
		height: 30px;
        
	}
	.tab-inactive {
		border-radius: 4px;
		color: $text-dark;
		background: $bg-white;
		width: 100%;
        height: 100%;
		font: $h6-medium;
        display: grid;
		place-items: center;
	}
</style>
