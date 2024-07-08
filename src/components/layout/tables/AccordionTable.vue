<template>
	<div class="table">
		<div :class="['table-header', {'table-minified': !tableDataVisible}]"  @click="setTableDataVisible">
			<div class="table-header__title">{{ text }}</div>
			<svg
				:class="{ 'chevron-down': !tableDataVisible }"
				width="10"
				height="6"
				viewBox="0 0 10 6"
				fill="none"
				xmlns="http://www.w3.org/2000/svg">
				<path
					d="M9 5L5 1L1 5"
					stroke="gray"
					stroke-width="1.5"
					stroke-linecap="round"
					stroke-linejoin="round" />
			</svg>
		</div>
		<div
			:class="
				tableDataVisible ? 'table-data-visible' : 'table-data-hidden'
			">
			<slot></slot>
		</div>
	</div>
</template>

<script setup>
	import { ref } from "vue";
	defineProps({
		text: String,
	});
	const tableDataVisible = ref(true);
	const setTableDataVisible = () => {
		tableDataVisible.value = !tableDataVisible.value;
	};
</script>

<style lang="scss" scoped>
	@import "@/styles/global";
	.table {
		border-radius: 4px;
		width: 100%;
		background: #F2F2F2;
		padding: 1px;
		box-shadow: 0 4px 4px 0 rgba(0, 0, 0, 0.25);
	}
	.table-header {
		display: flex;
		align-items: center;
		justify-content: space-between;
		padding: 11.5px 15px;
		background: #D0EAFA;
		border-radius: 3px 3px 0 0;
	}
	.table-minified{
		border-radius: 3px;
	}
	.table-header__title {
		font: normal 600 13px/140% "Noto Sans", sans-serif;
	}
	.button {
		padding: 5px 0 5px 5px;
	}
	.chevron-down {
		transform: rotate(180deg);
	}
	.table-data-visible{
		border-bottom-left-radius: 3px;
		border-bottom-right-radius: 3px;
		overflow-y: hidden;
	}
	.table-data-hidden {
		display: none;
	}
</style>
