<template>
	<div class="recovery-bg">
		<div class="recovery-border-container">
			<div class="recovery-border">
				<img src="@/assets/images/log-balls.png" class="balls" />
				<img src="@/assets/images/log-ball.png" class="ball" />
				<div class="recovery">
					<div class="recovery-container">
						<img
							src="@/components/icons/logo-light.svg"
							class="recovery__logo" />
						<h1 class="recovery__title">Access recovery</h1>
						<form action="" class="recovery__form">
							<input
								class="form__name"
								type="text"
								v-model="nameState"
								placeholder="Phone number or email" />
							<input
								class="form__code"
								type="text"
								v-model="codeState"
								placeholder="Verification code*" />
							<div class="password-container">
								<input
									class="form__password"
									:type="
										isPasswordVisible ? 'text' : 'password'
									"
									v-model="passwordState"
									placeholder="Create password" />
								<i
									:class="
										isPasswordVisible
											? 'icon-show'
											: 'icon-hide'
									"
									@click="handlePasswordClick"></i>
							</div>
							<div class="password-container">
								<input
									class="form__password"
									:type="
										isPasswordRepeatedVisible
											? 'text'
											: 'password'
									"
									v-model="passwordRepeatedState"
									placeholder="Repeat password" />
								<i
									:class="
										isPasswordRepeatedVisible
											? 'icon-show'
											: 'icon-hide'
									"
									@click="handlePasswordRepeatedClick"></i>
							</div>
						</form>
						<p class="new-code">
							Didn`t receive the code? You can request a new code
							in <span class="new-code__timer">59</span> seconds
						</p>
						<div class="restore-button">
							<ButtonLarge text="Will reset the password" />
						</div>
						<div class="register-button">
							<router-link to="register">
								<ButtonLarge
									text="Registration"
									type="secondary" />
							</router-link>
						</div>
					</div>
					<div class="login-button">
						<h5 class="login-button__title">Login</h5>
						<svg
							class="login-button__arrow"
							width="23"
							height="12"
							viewBox="0 0 23 12"
							fill="none"
							xmlns="http://www.w3.org/2000/svg">
							<path
								d="M22.5303 6.53033C22.8232 6.23744 22.8232 5.76256 22.5303 5.46967L17.7574 0.696699C17.4645 0.403806 16.9896 0.403806 16.6967 0.696699C16.4038 0.989592 16.4038 1.46447 16.6967 1.75736L20.9393 6L16.6967 10.2426C16.4038 10.5355 16.4038 11.0104 16.6967 11.3033C16.9896 11.5962 17.4645 11.5962 17.7574 11.3033L22.5303 6.53033ZM0 6.75H22V5.25H0V6.75Z"
								fill="#1F9DCD" />
						</svg>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script setup>
	import { ref, computed } from 'vue';
	import ButtonLarge from '@/components/layout/buttons/ButtonLarge.vue';
	import { useToast } from 'vue-toastification';

	const toast = useToast();
	const nameState = ref('');
	const codeState = ref('');
	const passwordState = ref('');
	const passwordRepeatedState = ref('');
	const isPasswordVisible = ref(false);
	const isPasswordRepeatedVisible = ref(false);
	const handlePasswordClick = () => {
		isPasswordVisible.value = !isPasswordVisible.value;
	};
	const handlePasswordRepeatedClick = () => {
		isPasswordRepeatedVisible.value = !isPasswordRepeatedVisible.value;
	};
	const codeError = computed(() => {
		return codeState.value === '0';
	});
	if (codeError) {
		toast('The code is not correct try again');
	}
</script>

<style lang="scss" scoped>
	@import '@/styles/global';
	.recovery-bg {
		position: relative;
		z-index: 1;
		overflow: scroll;
		padding: 125px 8px 50px;
		width: 100vw;
		overflow: hidden;
		height: 100%;
		min-height: 100dvh;
		background: radial-gradient(
			76.09% 34.16% at 51.6% 0%,
			#7ad7fc 0%,
			#2991ba 35.5953186750412%,
			rgb(212, 212, 212) 72.98812866210938%
		);
	}
	.recovery-border {
		position: relative;
		margin: 0 auto;
		padding: 1px;
		display: flex;
		justify-content: center;
		align-items: center;
		max-width: 361px;
		height: 100%;
		border-radius: 12px;
		background: linear-gradient(
			180deg,
			#248db6 27%,
			rgba(255, 255, 255, 0) 55%
		);
	}
	.balls {
		position: absolute;
		z-index: -1;
		top: -95px;
		left: calc(50% - 6px);
		transform: translateX(-50%);
		min-width: 352px;
	}
	.ball {
		position: absolute;
		z-index: 11;
		top: -83px;
		left: calc(50% + 108px);
		transform: translateX(-50%);
	}
	.recovery-border-container {
		height: 100%;
		max-width: 361px;
		margin: 0 auto;
		position: relative;
		z-index: 10;
	}
	.recovery {
		width: 100%;
		height: 100%;
		border-radius: 12px;
		overflow: scroll;
		color: $text-dark;
		background: $bg-white;
		box-shadow: 0 12px 16px 0 #ffffff2d,
			inset 0 -2px 4px 0 rgba(0, 0, 0, 0.42),
			0 -4px 6px 0 rgba(36, 141, 182, 0.6),
			inset 0 4px 4px 0 rgba(36, 141, 182, 0.6);
	}
	.recovery-container {
		padding: 24px 17px 15px 17px;
		height: 100%;
	}
	.recovery__logo {
		width: 117px;
		height: 17px;
	}
	.recovery__title {
		letter-spacing: -1px;
		margin-top: 57px;
		font: normal 600 40px/120% 'Noto Sans', sans-serif;
	}
	.recovery__form {
		margin: 16px auto 0;
		font: $h5-regular;
	}
	.form__name {
		padding: 14.5px 8px;
		height: 46px;
		width: 100%;
		background: $bg-white;
		border: none;
		color: $text-dark;
		border-radius: 4px;
	}
	.form__code {
		margin-top: 12px;
		padding: 14.5px 8px;
		height: 46px;
		width: 100%;
		background: $bg-white;
		border: none;
		color: $text-dark;
		border-radius: 4px;
	}
	.form__password {
		padding: 14.5px 8px;
		margin-top: 12px;
		height: 46px;
		width: 100%;
		background: $bg-white;
		border: none;
		color: $text-dark;
		border-radius: 4px;
	}
	.icon-show {
		position: relative;
	}
	.icon-hide {
		position: relative;
	}
	.icon-hide::before {
		position: absolute;
		content: '';
		top: 50%;
		transform: translateY(-50%);
		right: 13px;
		width: 20px;
		height: 20px;
		background: url('data:image/svg+xml,<svg width="20" height="20" viewBox="0 0 20 20" fill="none" xmlns="http://www.w3.org/2000/svg"><g clip-path="url(%23clip0_2243_345)"><path d="M8.25016 3.53352C8.82377 3.39925 9.41105 3.33213 10.0002 3.33352C15.8335 3.33352 19.1668 10.0002 19.1668 10.0002C18.661 10.9465 18.0577 11.8375 17.3668 12.6585M11.7668 11.7669C11.538 12.0125 11.262 12.2095 10.9553 12.3461C10.6486 12.4828 10.3176 12.5562 9.9819 12.5622C9.64623 12.5681 9.3128 12.5063 9.0015 12.3806C8.69021 12.2549 8.40743 12.0677 8.17003 11.8303C7.93264 11.5929 7.74549 11.3101 7.61975 10.9988C7.49402 10.6875 7.43227 10.3541 7.43819 10.0184C7.44411 9.68277 7.51759 9.35172 7.65423 9.04506C7.79087 8.73839 7.98787 8.46239 8.2335 8.23352M14.9502 14.9502C13.5257 16.036 11.7911 16.6376 10.0002 16.6669C4.16683 16.6669 0.833496 10.0002 0.833496 10.0002C1.87007 8.06843 3.30778 6.38069 5.05016 5.05018L14.9502 14.9502Z" stroke="%235E6471" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" /><path d="M0.833496 0.833496L19.1668 19.1668" stroke="%235E6471" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" /></g><defs><clipPath id="clip0_2243_345"><rect width="20" height="20" fill="white" /></clipPath></defs></svg>');
	}
	.icon-show::before {
		position: absolute;
		content: '';
		top: 50%;
		transform: translateY(-50%);
		right: 13px;
		width: 20px;
		height: 16px;
		background: url('data:image/svg+xml,<svg width="20" height="16" viewBox="0 0 20 16" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M0.833008 8.00016C0.833008 8.00016 4.16634 1.3335 9.99967 1.3335C15.833 1.3335 19.1663 8.00016 19.1663 8.00016C19.1663 8.00016 15.833 14.6668 9.99967 14.6668C4.16634 14.6668 0.833008 8.00016 0.833008 8.00016Z" stroke="%235E6471" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" /><path d="M10 10.5C11.3807 10.5 12.5 9.38071 12.5 8C12.5 6.61929 11.3807 5.5 10 5.5C8.61929 5.5 7.5 6.61929 7.5 8C7.5 9.38071 8.61929 10.5 10 10.5Z" stroke="%235E6471" stroke-width="1.5" stroke-linecap="round" stroke-linejoin="round" /></svg>');
	}
	input:focus {
		outline: none;
	}
	.new-code {
		margin-top: 8px;
		font: $h4-medium;
		color: $text-dark;
	}
	.new-code__timer {
		background: $bg-white;
		color: $text-accent-blue;
		border: 1px solid rgba(1, 1, 1, 0.2);
		border-radius: 4px;
		padding: 1px 4px;
	}
	.restore-button {
		margin-top: 20px;
	}
	.register-button {
		margin-top: 60px;
	}
	.login-button {
		background: linear-gradient(
			180deg,
			rgba(153, 153, 153, 0.25) 0%,
			rgba(0, 0, 0, 0) 100%
		);
		padding: 15px 35px 14px 33px;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.login-button__title {
		font: $h5-regular;
		color: $text-accent-blue;
	}
</style>
