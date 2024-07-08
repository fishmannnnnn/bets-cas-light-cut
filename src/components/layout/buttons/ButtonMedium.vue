<script setup>
	const props = defineProps({
		type: {
			type: String,
			default: 'primary',
		},
		className: {
			type: String,
		},
		text: {
			type: String,
		},
	});
</script>
<template>
	<div :class="['btn', `btn_${type}`, className]">
		<div :class="['button-bg', `button-bg_${type}`]">
			<div class="rect-border">
				<div :class="['bg__rect', `bg__rect-${type}`]"></div>
			</div>
			<div :class="['bg__right', `bg__right-${type}`]"></div>
		</div>
		<div class="container">
			<span v-if="text">{{ text }}</span>
			<span v-else-if="type === 'primary' || type === 'primary-disabled'"
				>Registration</span
			>
			<span v-else>Login</span>
			<slot></slot>
		</div>
	</div>
</template>

<style lang="scss" scoped>
	@import '@/styles/global';
	.btn {
		color: white;
		position: relative;
		width: 100%;
		height: 45px;
		border: none;
		font: $h5-medium;
		&_primary {
			&-disabled {
				opacity: 0.5;
			}
		}
		&_secondary {
			color: $text-accent-blue;
			&-disabled {
				color: $text-accent-blue;
				opacity: 0.5;
			}
		}
	}
	.button-bg {
		position: relative;
		&_primary {
			filter: drop-shadow(0 0 3px rgba(100, 210, 255, 0.44))
				drop-shadow(0 0 2px rgba(0, 0, 0, 0.12));
			&-disabled {
				filter: drop-shadow(0 0 3px rgba(100, 210, 255, 0.44))
					drop-shadow(0 0 2px rgba(0, 0, 0, 0.12));
			}
		}
		&_secondary {
			filter: drop-shadow(0 0 3px rgba(100, 210, 255, 0.44))
				drop-shadow(0 0 2px rgba(0, 0, 0, 0.12));
			&-disabled {
				filter: drop-shadow(0 0 3px rgba(100, 210, 255, 0.44))
					drop-shadow(0 0 2px rgba(0, 0, 0, 0.12));
			}
		}
	}
	.rect-border {
		width: calc(100% - 19px);
		padding: 1px;
		padding-right: 0;
		border-radius: 8px;
		border-top-right-radius: 0;
		border-bottom-right-radius: 0;
		height: 44px;
		background: rgba(70, 244, 255, 1);
	}
	.bg__rect {
		width: 100%;
		height: 100%;
		border-radius: 8px;
		border-top-right-radius: 0;
		border-bottom-right-radius: 0;
		&-primary {
			background: linear-gradient(0deg, #1b94c3 0%, #7dd9ff 100%);
			&-disabled {
				background: linear-gradient(0deg, #1b94c3 0%, #7dd9ff 100%);
			}
		}
		&-secondary {
			background: white;
			&-disabled {
				background: white;
			}
		}
	}
	.bg__right {
		position: absolute;
		width: 20px;
		height: 45px;
		top: 0;
		right: 0;
		&-primary {
			background: url('data:image/svg+xml,<svg width="20" height="45" viewBox="0 0 20 45" fill="none" xmlns="http://www.w3.org/2000/svg"><mask id="mask0_124_28" style="mask-type:alpha" maskUnits="userSpaceOnUse" x="0" y="0" width="20" height="45"><rect width="20" height="45" fill="%23D9D9D9" /></mask><g mask="url(%23mask0_124_28)"><path d="M-322 0.5H15C16.933 0.5 18.5 2.067 18.5 4V26.8431C18.5 27.7714 18.1313 28.6616 17.4749 29.318L4.31802 42.4749C3.66165 43.1312 2.77139 43.5 1.84314 43.5H-322C-323.933 43.5 -325.5 41.933 -325.5 40V4C-325.5 2.067 -323.933 0.5 -322 0.5Z" fill="url(%23paint0_linear_124_28)" stroke="url(%23paint1_linear_124_28)" /><path d="M18.5 42.5V36.9142C18.5 36.0233 17.4229 35.5771 16.7929 36.2071L11.2071 41.7929C10.5771 42.4229 11.0233 43.5 11.9142 43.5H17.5C18.0523 43.5 18.5 43.0523 18.5 42.5Z" fill="%233097C0" stroke="%2346F4FF" /></g><defs><linearGradient id="paint0_linear_124_28" x1="-127.5" y1="44" x2="-127.5" y2="6.48473e-07" gradientUnits="userSpaceOnUse"><stop stop-color="%231B94C4" /><stop offset="1" stop-color="%237DD9FF" /></linearGradient><linearGradient id="paint1_linear_124_28" x1="-17.5" y1="39" x2="-215.5" y2="-7.37427e-06" gradientUnits="userSpaceOnUse"><stop stop-color="%2346F4FF" /><stop offset="1" stop-color="%232991BA" stop-opacity="0" /></linearGradient></defs></svg>');
			&-disabled {
				background: url('data:image/svg+xml,<svg width="20" height="45" viewBox="0 0 20 45" fill="none" xmlns="http://www.w3.org/2000/svg"><mask id="mask0_124_28" style="mask-type:alpha" maskUnits="userSpaceOnUse" x="0" y="0" width="20" height="45"><rect width="20" height="45" fill="%23D9D9D9" /></mask><g mask="url(%23mask0_124_28)"><path d="M-322 0.5H15C16.933 0.5 18.5 2.067 18.5 4V26.8431C18.5 27.7714 18.1313 28.6616 17.4749 29.318L4.31802 42.4749C3.66165 43.1312 2.77139 43.5 1.84314 43.5H-322C-323.933 43.5 -325.5 41.933 -325.5 40V4C-325.5 2.067 -323.933 0.5 -322 0.5Z" fill="url(%23paint0_linear_124_28)" stroke="url(%23paint1_linear_124_28)" /><path d="M18.5 42.5V36.9142C18.5 36.0233 17.4229 35.5771 16.7929 36.2071L11.2071 41.7929C10.5771 42.4229 11.0233 43.5 11.9142 43.5H17.5C18.0523 43.5 18.5 43.0523 18.5 42.5Z" fill="%233097C0" stroke="%2346F4FF" /></g><defs><linearGradient id="paint0_linear_124_28" x1="-127.5" y1="44" x2="-127.5" y2="6.48473e-07" gradientUnits="userSpaceOnUse"><stop stop-color="%231B94C4" /><stop offset="1" stop-color="%237DD9FF" /></linearGradient><linearGradient id="paint1_linear_124_28" x1="-17.5" y1="39" x2="-215.5" y2="-7.37427e-06" gradientUnits="userSpaceOnUse"><stop stop-color="%2346F4FF" /><stop offset="1" stop-color="%232991BA" stop-opacity="0" /></linearGradient></defs></svg>');
			}
		}
		&-secondary {
			background: url('data:image/svg+xml,<svg width="20" height="45" viewBox="0 0 20 45" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M-322 0.5H15C16.933 0.5 18.5 2.067 18.5 4V26.8431C18.5 27.7714 18.1313 28.6616 17.4749 29.318L4.31802 42.4749C3.66165 43.1312 2.77139 43.5 1.84314 43.5H-322C-323.933 43.5 -325.5 41.933 -325.5 40V4C-325.5 2.067 -323.933 0.5 -322 0.5Z" fill="url(%23paint0_linear_131_8)" stroke="url(%23paint1_linear_131_8)" /><path d="M19 43V37.4142C19 36.5233 17.9229 36.0771 17.2929 36.7071L11.7071 42.2929C11.0771 42.9229 11.5233 44 12.4142 44H18C18.5523 44 19 43.5523 19 43Z" fill="white" stroke="%2346F4FF" /><defs><linearGradient id="paint0_linear_131_8" x1="-127.5" y1="44" x2="-127.5" y2="6.48473e-07" gradientUnits="userSpaceOnUse"><stop stop-color="white" /><stop offset="1" stop-color="white" /></linearGradient><linearGradient id="paint1_linear_131_8" x1="-17.5" y1="39" x2="-215.5" y2="-7.37427e-06" gradientUnits="userSpaceOnUse"><stop stop-color="%2346F4FF" /><stop offset="1" stop-color="%232991BA" stop-opacity="0" /></linearGradient></defs></svg>');
			&-disabled {
				background: url('data:image/svg+xml,<svg width="20" height="45" viewBox="0 0 20 45" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M-322 0.5H15C16.933 0.5 18.5 2.067 18.5 4V26.8431C18.5 27.7714 18.1313 28.6616 17.4749 29.318L4.31802 42.4749C3.66165 43.1312 2.77139 43.5 1.84314 43.5H-322C-323.933 43.5 -325.5 41.933 -325.5 40V4C-325.5 2.067 -323.933 0.5 -322 0.5Z" fill="url(%23paint0_linear_131_8)" stroke="url(%23paint1_linear_131_8)" /><path d="M19 43V37.4142C19 36.5233 17.9229 36.0771 17.2929 36.7071L11.7071 42.2929C11.0771 42.9229 11.5233 44 12.4142 44H18C18.5523 44 19 43.5523 19 43Z" fill="white" stroke="%2346F4FF" /><defs><linearGradient id="paint0_linear_131_8" x1="-127.5" y1="44" x2="-127.5" y2="6.48473e-07" gradientUnits="userSpaceOnUse"><stop stop-color="white" /><stop offset="1" stop-color="white" /></linearGradient><linearGradient id="paint1_linear_131_8" x1="-17.5" y1="39" x2="-215.5" y2="-7.37427e-06" gradientUnits="userSpaceOnUse"><stop stop-color="%2346F4FF" /><stop offset="1" stop-color="%232991BA" stop-opacity="0" /></linearGradient></defs></svg>');
			}
		}
	}
	.container {
		width: 100%;
		position: absolute;
		top: 0;
		left: 0;
		display: flex;
		justify-content: space-between;
		padding: 14px 20px 14px 16px;
	}
</style>
