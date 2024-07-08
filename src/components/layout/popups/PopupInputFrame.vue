<template>
	<div :class="'frame-border-' + type">
		<div :class="'frame-inside-' + type">
			{{ value }}
		</div>
	</div>
</template>

<script setup>
	defineProps({
		type: String,
		value: Number,
	});
</script>

<style lang="scss" scoped>
	@import "@/styles/global";
	.frame-border-inactive {
        border-radius: 4px;
		width: 76px;
		height: 30px;
		padding: 1px;
		background: white;
		box-shadow: 0 0 2px rgba(0,0,0, 0.5);
	}
	.frame-inside-inactive {
        width: 100%;
        height: 100%;
        border-radius: 3px;
		background: $bg-white;
		box-shadow: inset 0 -2px 4px 0 rgba(255, 255, 255, 0.1);
		display: flex;
		align-items: center;
		justify-content: space-around;
		font: $h4-medium;
	}
	.frame-border-active {
        border-radius: 4px;
		width: 76px;
		height: 30px;
		padding: 1px;
		background: $text-blue-stroke;
	}
	.frame-inside-active {
        width: 100%;
        height: 100%;
        border-radius: 3px;
		background: $accent-blue-gradient;
		box-shadow: inset 0 -2px 4px 0 rgba(255, 255, 255, 0.1);
		display: flex;
		align-items: center;
		justify-content: space-around;
		font: $h4-medium;
        color: white;
	}
</style>
