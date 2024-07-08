<template>
	<div class="progress-bar">
		<div class="bg-bar">
			<div
				class="bar color color-gradient"
				:style="`width: ${progress}%`"></div>
		</div>
		<div class="points">
			<div :class="['point', progress >= 0 ? 'color' : '']"></div>
			<div :class="['point', progress >= 50 ? 'color' : '']"></div>
			<div :class="['point', progress >= 100 ? 'color' : '']"></div>
		</div>
	</div>
</template>

<script setup>
	defineProps({
		progress: String,
	});
</script>

<style lang="scss" scoped>
	.progress-bar {
		position: relative;
		z-index: 2;
	}
	.points {
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.point {
		width: 4px;
		height: 14px;
		border-radius: 12px;
		background: #d9d9d9;
	}
	.bg-bar {
		position: absolute;
		z-index: -1;
		top: 5px;
		width: 100%;
		height: 4px;
		background: #d9d9d9;
	}
	.bar {
		overflow-x: hidden;
		height: 4px;
	}
	.color {
		background: #25d8f8;
		box-shadow: 0 0 12px 0 rgba(79, 220, 255, 0.6), 0 0 2px 0 #4fdcff;
	}
	.color-gradient {
		background: linear-gradient(270deg, #6ef5ff 0%, #41aaff 100%);
	}
</style>
