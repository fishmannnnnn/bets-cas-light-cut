<template>
	<div class="data-container">
		<div class="data">
			<svg
				@click="handleStarClick"
				class="star"
				width="19"
				height="18"
				viewBox="0 0 19 18"
				fill="none"
				xmlns="http://www.w3.org/2000/svg">
				<path
					:class="starActive ? 'star-active' : 'star-inactive'"
					fill-rule="evenodd"
					clip-rule="evenodd"
					d="M9.5 1C9.79412 1 10.0627 1.16447 10.1929 1.42426L12.401 5.8308L17.339 6.54178C17.63 6.58367 17.8716 6.78463 17.9623 7.06018C18.053 7.33574 17.9771 7.63812 17.7664 7.84023L14.1939 11.2678L15.037 16.1101C15.0868 16.3957 14.9676 16.6844 14.7296 16.8547C14.4916 17.025 14.1761 17.0474 13.9158 16.9125L9.5 14.625L5.08422 16.9125C4.82388 17.0474 4.50838 17.025 4.2704 16.8547C4.03242 16.6844 3.91323 16.3957 3.96295 16.1101L4.80606 11.2678L1.23359 7.84023C1.02293 7.63812 0.946995 7.33574 1.0377 7.06018C1.1284 6.78463 1.37001 6.58367 1.66099 6.54178L6.59899 5.8308L8.80709 1.42426C8.93727 1.16447 9.20589 1 9.5 1Z"
					fill="none"
					stroke="none"
					stroke-linecap="round"
					stroke-linejoin="round" />
			</svg>
			<div class="id-container">
				<div class="id">{{ data.id }}</div>
				<div class="id-container-right">
					<svg
						v-if="data.hasInfo"
						width="15"
						height="15"
						viewBox="0 0 15 15"
						fill="none"
						xmlns="http://www.w3.org/2000/svg">
						<path
							fill-rule="evenodd"
							clip-rule="evenodd"
							d="M7.50024 1.2C4.02071 1.2 1.2 4.02071 1.2 7.50024C1.2 10.9798 4.02071 13.8005 7.50024 13.8005C10.9798 13.8005 13.8005 10.9798 13.8005 7.50024C13.8005 4.02071 10.9798 1.2 7.50024 1.2ZM0 7.50024C0 3.35797 3.35797 0 7.50024 0C11.6425 0 15.0005 3.35797 15.0005 7.50024C15.0005 11.6425 11.6425 15.0005 7.50024 15.0005C3.35797 15.0005 0 11.6425 0 7.50024ZM7.49917 6.9043C7.83054 6.9043 8.09917 7.17293 8.09917 7.5043V10.2644C8.09917 10.5958 7.83054 10.8644 7.49917 10.8644C7.1678 10.8644 6.89917 10.5958 6.89917 10.2644V7.5043C6.89917 7.17293 7.1678 6.9043 7.49917 6.9043ZM7.49917 4.14258C7.1678 4.14258 6.89917 4.41121 6.89917 4.74258C6.89917 5.07395 7.1678 5.34258 7.49917 5.34258H7.50667C7.83804 5.34258 8.10667 5.07395 8.10667 4.74258C8.10667 4.41121 7.83804 4.14258 7.50667 4.14258H7.49917Z"
							fill="gray" />
					</svg>
					<svg
						v-if="data.hasLive"
						width="15"
						height="15"
						viewBox="0 0 15 15"
						fill="none"
						xmlns="http://www.w3.org/2000/svg">
						<path
							fill-rule="evenodd"
							clip-rule="evenodd"
							d="M3.59688 0.349582C3.79213 0.154314 4.10872 0.154305 4.30398 0.349562L7.40095 3.44635L10.4979 0.349562C10.6932 0.154305 11.0098 0.154314 11.205 0.349582C11.4003 0.544849 11.4003 0.861432 11.205 1.05669L8.61115 3.65039H12.9223C13.9607 3.65039 14.8025 4.49212 14.8025 5.53052V13.1212C14.8025 14.1596 13.9607 15.0013 12.9223 15.0013H1.88069C0.84231 15.0013 0.000488281 14.1596 0.000488281 13.1212V5.53052C0.000488281 4.49212 0.84231 3.65039 1.88069 3.65039H6.19075L3.5969 1.05669C3.40163 0.861432 3.40162 0.544849 3.59688 0.349582ZM7.45621 4.65039C7.41949 4.65445 7.3824 4.65445 7.34568 4.65039H1.88069C1.39454 4.65039 1.00049 5.04446 1.00049 5.53052V13.1212C1.00049 13.6073 1.39454 14.0013 1.88069 14.0013H12.9223C13.4085 14.0013 13.8025 13.6073 13.8025 13.1212V5.53052C13.8025 5.04446 13.4085 4.65039 12.9223 4.65039H7.45621ZM6.50099 6.64513C6.30322 6.49681 6.021 6.63793 6.021 6.88514V11.2057C6.021 11.4529 6.30322 11.594 6.50099 11.4457L9.38151 9.28541C9.54152 9.16541 9.54152 8.9254 9.38151 8.8054L6.50099 6.64513Z"
							fill="gray" />
					</svg>
					<svg
						v-if="data.hasField"
						width="18"
						height="13"
						viewBox="0 0 18 13"
						fill="none"
						xmlns="http://www.w3.org/2000/svg">
						<path
							fill-rule="evenodd"
							clip-rule="evenodd"
							d="M9.80249 1H16.1025C16.4709 1 16.8025 1.30993 16.8025 1.73333V11.2667C16.8025 11.6901 16.4709 12 16.1025 12H9.80249V10.9725C12.0525 10.7238 13.8025 8.81628 13.8025 6.5C13.8025 4.18372 12.0525 2.27619 9.80249 2.02746V1ZM12.8025 6.5C12.8025 8.26324 11.4986 9.72194 9.80249 9.96456V7.91465C10.3851 7.70873 10.8025 7.15311 10.8025 6.5C10.8025 5.84689 10.3851 5.29127 9.80249 5.08535V3.03544C11.4986 3.27806 12.8025 4.73676 12.8025 6.5ZM8.80249 5.08535V3.03544C7.10634 3.27806 5.80249 4.73676 5.80249 6.5C5.80249 8.26324 7.10634 9.72194 8.80249 9.96456V7.91465C8.21989 7.70873 7.80249 7.15311 7.80249 6.5C7.80249 5.84689 8.21989 5.29127 8.80249 5.08535ZM4.80249 6.5C4.80249 4.18372 6.55252 2.27619 8.80249 2.02746V1H2.50249C2.13411 1 1.80249 1.30993 1.80249 1.73333V11.2667C1.80249 11.6901 2.13411 12 2.50249 12H8.80249V10.9725C6.55252 10.7238 4.80249 8.81628 4.80249 6.5ZM8.80249 0H9.80249H16.1025C17.0414 0 17.8025 0.77604 17.8025 1.73333V11.2667C17.8025 12.224 17.0414 13 16.1025 13H9.80249H8.80249H2.50249C1.56361 13 0.80249 12.224 0.80249 11.2667V1.73333C0.80249 0.77604 1.56361 0 2.50249 0H8.80249Z"
							fill="gray" />
					</svg>
					<svg
						v-if="data.hasStatistics"
						class="stats"
						width="13"
						height="13"
						viewBox="0 0 13 13"
						fill="none"
						xmlns="http://www.w3.org/2000/svg">
						<path
							fill-rule="evenodd"
							clip-rule="evenodd"
							d="M2 1H11C11.5523 1 12 1.44772 12 2V11C12 11.5523 11.5523 12 11 12H10.4815C10.4936 11.9465 10.5 11.8908 10.5 11.8337V3.16699C10.5 2.75278 10.1642 2.41699 9.75 2.41699C9.33579 2.41699 9 2.75278 9 3.16699V11.8337C9 11.8908 9.0064 11.9465 9.01851 12H7.23149C7.2436 11.9465 7.25 11.8908 7.25 11.8337V6.41699C7.25 6.00278 6.91421 5.66699 6.5 5.66699C6.08579 5.66699 5.75 6.00278 5.75 6.41699V11.8337C5.75 11.8908 5.7564 11.9465 5.76851 12H3.98149C3.9936 11.9465 4 11.8908 4 11.8337V9.66699C4 9.25278 3.66421 8.91699 3.25 8.91699C2.83579 8.91699 2.5 9.25278 2.5 9.66699V11.8337C2.5 11.8908 2.5064 11.9465 2.51851 12H2C1.44772 12 1 11.5523 1 11V2C1 1.44772 1.44772 1 2 1ZM0 2C0 0.89543 0.895431 0 2 0H11C12.1046 0 13 0.895431 13 2V11C13 12.1046 12.1046 13 11 13H2C0.89543 13 0 12.1046 0 11V2Z"
							fill="gray" />
					</svg>
				</div>
			</div>
		</div>
		<div class="container-teams-date">
			<div class="teams">
				<div
					class="team"
					v-for="(item, index) in data.teams"
					:key="index">
					{{ item }}
				</div>
			</div>
			<div class="teams-date-container">
				<svg
					v-if="data.hasBreak"
					class="break"
					width="56"
					height="38"
					viewBox="0 0 56 38"
					fill="none"
					xmlns="http://www.w3.org/2000/svg">
					<g filter="url(#filter0_d_4901_23938)">
						<mask id="path-1-inside-1_4901_23938" fill="white">
							<path
								fill-rule="evenodd"
								clip-rule="evenodd"
								d="M8 4C5.79086 4 4 5.79086 4 8V23C4 25.2091 5.79086 27 8 27H21.4437L27.2929 32.8492C27.6834 33.2398 28.3166 33.2398 28.7071 32.8492L34.5563 27H48C50.2091 27 52 25.2091 52 23V8C52 5.79086 50.2091 4 48 4H8Z" />
						</mask>
						<path
							fill-rule="evenodd"
							clip-rule="evenodd"
							d="M8 4C5.79086 4 4 5.79086 4 8V23C4 25.2091 5.79086 27 8 27H21.4437L27.2929 32.8492C27.6834 33.2398 28.3166 33.2398 28.7071 32.8492L34.5563 27H48C50.2091 27 52 25.2091 52 23V8C52 5.79086 50.2091 4 48 4H8Z"
							fill="black" />
						<path
							d="M21.4437 27L22.1508 26.2929L21.8579 26H21.4437V27ZM34.5563 27V26H34.1421L33.8492 26.2929L34.5563 27ZM5 8C5 6.34315 6.34315 5 8 5V3C5.23858 3 3 5.23858 3 8H5ZM5 23V8H3V23H5ZM8 26C6.34315 26 5 24.6569 5 23H3C3 25.7614 5.23857 28 8 28V26ZM21.4437 26H8V28H21.4437V26ZM28 32.1421L22.1508 26.2929L20.7365 27.7071L26.5858 33.5563L28 32.1421ZM28 32.1421L26.5858 33.5563C27.3668 34.3374 28.6332 34.3374 29.4142 33.5563L28 32.1421ZM33.8492 26.2929L28 32.1421L29.4142 33.5563L35.2635 27.7071L33.8492 26.2929ZM48 26H34.5563V28H48V26ZM51 23C51 24.6569 49.6569 26 48 26V28C50.7614 28 53 25.7614 53 23H51ZM51 8V23H53V8H51ZM48 5C49.6569 5 51 6.34315 51 8H53C53 5.23858 50.7614 3 48 3V5ZM8 5H48V3H8V5Z"
							fill="url(#paint0_linear_4901_23938)"
							mask="url(#path-1-inside-1_4901_23938)" />
					</g>
					<path
						d="M13.913 9.718C14.6843 9.718 15.33 9.79167 15.85 9.939C16.3787 10.0863 16.773 10.329 17.033 10.667C17.3017 11.005 17.436 11.4557 17.436 12.019C17.436 12.383 17.3667 12.708 17.228 12.994C17.098 13.2713 16.8987 13.5053 16.63 13.696C16.37 13.878 16.0493 14.0037 15.668 14.073V14.138C16.058 14.1987 16.409 14.3113 16.721 14.476C17.0417 14.6407 17.293 14.8747 17.475 15.178C17.657 15.4813 17.748 15.8757 17.748 16.361C17.748 16.9243 17.618 17.4053 17.358 17.804C17.098 18.194 16.7253 18.493 16.24 18.701C15.7633 18.9003 15.1913 19 14.524 19H11.261V9.718H13.913ZM14.147 13.67C14.9443 13.67 15.4903 13.5443 15.785 13.293C16.0797 13.033 16.227 12.6517 16.227 12.149C16.227 11.6377 16.045 11.2737 15.681 11.057C15.3257 10.8317 14.7537 10.719 13.965 10.719H12.431V13.67H14.147ZM12.431 14.645V18.012H14.303C15.1263 18.012 15.6983 17.8517 16.019 17.531C16.3397 17.2103 16.5 16.79 16.5 16.27C16.5 15.9407 16.4263 15.6547 16.279 15.412C16.1403 15.1693 15.902 14.983 15.564 14.853C15.2347 14.7143 14.784 14.645 14.212 14.645H12.431ZM22.8101 11.902C22.9401 11.902 23.0787 11.9107 23.2261 11.928C23.3821 11.9367 23.5164 11.954 23.6291 11.98L23.4861 13.033C23.3734 13.007 23.2477 12.9853 23.1091 12.968C22.9791 12.9507 22.8534 12.942 22.7321 12.942C22.4634 12.942 22.2077 12.9983 21.9651 13.111C21.7224 13.2237 21.5057 13.384 21.3151 13.592C21.1244 13.7913 20.9727 14.034 20.8601 14.32C20.7561 14.606 20.7041 14.9267 20.7041 15.282V19H19.5601V12.032H20.4961L20.6261 13.306H20.6781C20.8254 13.046 21.0031 12.812 21.2111 12.604C21.4191 12.3873 21.6574 12.2183 21.9261 12.097C22.1947 11.967 22.4894 11.902 22.8101 11.902ZM27.3673 11.902C27.9653 11.902 28.4766 12.032 28.9013 12.292C29.3346 12.552 29.664 12.9203 29.8893 13.397C30.1233 13.865 30.2403 14.4153 30.2403 15.048V15.737H25.4693C25.4866 16.5257 25.686 17.128 26.0673 17.544C26.4573 17.9513 26.999 18.155 27.6923 18.155C28.1343 18.155 28.5243 18.116 28.8623 18.038C29.209 17.9513 29.5643 17.83 29.9283 17.674V18.675C29.573 18.831 29.222 18.9437 28.8753 19.013C28.5286 19.091 28.117 19.13 27.6403 19.13C26.9816 19.13 26.3966 18.9957 25.8853 18.727C25.3826 18.4583 24.9883 18.0597 24.7023 17.531C24.425 16.9937 24.2863 16.3393 24.2863 15.568C24.2863 14.8053 24.412 14.151 24.6633 13.605C24.9233 13.059 25.283 12.6387 25.7423 12.344C26.2103 12.0493 26.752 11.902 27.3673 11.902ZM27.3543 12.838C26.8083 12.838 26.375 13.0157 26.0543 13.371C25.7423 13.7177 25.556 14.203 25.4953 14.827H29.0443C29.0443 14.4283 28.9836 14.0817 28.8623 13.787C28.741 13.4923 28.5546 13.2627 28.3033 13.098C28.0606 12.9247 27.7443 12.838 27.3543 12.838ZM34.6532 11.915C35.5025 11.915 36.1308 12.1013 36.5382 12.474C36.9455 12.8467 37.1492 13.4403 37.1492 14.255V19H36.3172L36.0962 18.012H36.0442C35.8448 18.2633 35.6368 18.4757 35.4202 18.649C35.2122 18.8137 34.9695 18.935 34.6922 19.013C34.4235 19.091 34.0942 19.13 33.7042 19.13C33.2882 19.13 32.9112 19.0563 32.5732 18.909C32.2438 18.7617 31.9838 18.5363 31.7932 18.233C31.6025 17.921 31.5072 17.531 31.5072 17.063C31.5072 16.3697 31.7802 15.8367 32.3262 15.464C32.8722 15.0827 33.7128 14.8747 34.8482 14.84L36.0312 14.801V14.385C36.0312 13.8043 35.9055 13.4013 35.6542 13.176C35.4028 12.9507 35.0475 12.838 34.5882 12.838C34.2242 12.838 33.8775 12.8943 33.5482 13.007C33.2188 13.111 32.9112 13.2323 32.6252 13.371L32.2742 12.513C32.5775 12.3483 32.9372 12.2097 33.3532 12.097C33.7692 11.9757 34.2025 11.915 34.6532 11.915ZM34.9912 15.633C34.1245 15.6677 33.5222 15.8063 33.1842 16.049C32.8548 16.2917 32.6902 16.634 32.6902 17.076C32.6902 17.466 32.8072 17.752 33.0412 17.934C33.2838 18.116 33.5915 18.207 33.9642 18.207C34.5535 18.207 35.0432 18.0467 35.4332 17.726C35.8232 17.3967 36.0182 16.894 36.0182 16.218V15.594L34.9912 15.633ZM40.4323 14.281C40.4323 14.4197 40.4236 14.6017 40.4063 14.827C40.3976 15.0523 40.389 15.2473 40.3803 15.412H40.4323C40.4843 15.3427 40.5623 15.243 40.6663 15.113C40.7703 14.983 40.8743 14.853 40.9783 14.723C41.091 14.5843 41.1863 14.4717 41.2643 14.385L43.4873 12.032H44.8263L42.0053 15.009L45.0213 19H43.6433L41.2253 15.75L40.4323 16.439V19H39.3013V9.12H40.4323V14.281Z"
						fill="white" />
					<defs>
						<filter
							id="filter0_d_4901_23938"
							x="0"
							y="0"
							width="56"
							height="37.1426"
							filterUnits="userSpaceOnUse"
							color-interpolation-filters="sRGB">
							<feFlood
								flood-opacity="0"
								result="BackgroundImageFix" />
							<feColorMatrix
								in="SourceAlpha"
								type="matrix"
								values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0"
								result="hardAlpha" />
							<feOffset />
							<feGaussianBlur stdDeviation="2" />
							<feComposite in2="hardAlpha" operator="out" />
							<feColorMatrix
								type="matrix"
								values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0.62 0" />
							<feBlend
								mode="normal"
								in2="BackgroundImageFix"
								result="effect1_dropShadow_4901_23938" />
							<feBlend
								mode="normal"
								in="SourceGraphic"
								in2="effect1_dropShadow_4901_23938"
								result="shape" />
						</filter>
						<linearGradient
							id="paint0_linear_4901_23938"
							x1="28"
							y1="4"
							x2="28"
							y2="33.1421"
							gradientUnits="userSpaceOnUse">
							<stop stop-color="#FEB424" />
							<stop
								offset="0.287312"
								stop-color="white"
								stop-opacity="0.4" />
							<stop
								offset="0.655"
								stop-color="white"
								stop-opacity="0.4" />
							<stop offset="1" stop-color="white" />
						</linearGradient>
					</defs>
				</svg>

				<div class="teams-date-score">{{ data.score }}</div>
				<div class="teams-date-time-container">
					<svg
						width="18"
						height="18"
						viewBox="0 0 18 18"
						fill="none"
						xmlns="http://www.w3.org/2000/svg">
						<g clip-path="url(#clip0_6236_16871)">
							<path
								d="M9 16.5C13.1421 16.5 16.5 13.1421 16.5 9C16.5 4.85786 13.1421 1.5 9 1.5C4.85786 1.5 1.5 4.85786 1.5 9C1.5 13.1421 4.85786 16.5 9 16.5Z"
								stroke="#00FC77"
								stroke-width="1.5"
								stroke-linecap="round"
								stroke-linejoin="round" />
							<path
								d="M9 4.5V9L12 10.5"
								stroke="#00FC77"
								stroke-width="1.5"
								stroke-linecap="round"
								stroke-linejoin="round" />
						</g>
						<defs>
							<clipPath id="clip0_6236_16871">
								<rect width="18" height="18" fill="white" />
							</clipPath>
						</defs>
					</svg>
					<div class="teams-date-time">{{ data.time }}</div>
				</div>
			</div>
		</div>
	</div>
	<div class="table-container-wrapper">
		<div class="table-container">
			<div class="table">
				<div
					class="first-row"
					v-for="(item, index) in data.table[0]"
					:key="index">
					{{ item }}
				</div>
				<div
					:class="[
						'second-row',
						index == data.accentField
							? `accentField-${props.data.accentColor}`
							: '',
					]"
					v-for="(item, index) in data.table[1]"
					:key="index">
					{{ item }}
				</div>
			</div>
		</div>
	</div>
</template>

<script setup>
	import { ref } from 'vue';
	const props = defineProps({
		data: Object,
	});
	const starActive = ref(false);
	const handleStarClick = () => {
		starActive.value = !starActive.value;
	};
</script>

<style lang="scss" scoped>
	@import '@/styles/global';
	.data-container {
		margin-top: 6px;
		padding: 8px 15px 0;
		background: $bg-white;
		height: 66px;
		box-shadow: 0 0 2px rgba(0, 0, 0, 0.25);
	}
	.data {
		display: flex;
		width: 100%;
		gap: 5px;
	}
	.star-active {
		fill: $gold-accent;
		stroke: $gold-accent;
	}
	.star-inactive {
		fill: $gray-icon;
		stroke: $gray-icon;
	}
	.id-container {
		width: 100%;
		display: flex;
		align-items: center;
		justify-content: space-between;
	}
	.id {
		font: $h7-regular;
		color: $gray-text;
	}
	.id-container-right {
		display: flex;
		gap: 20px;
		align-items: center;
	}
	.stats {
		margin-top: 2px;
		margin-left: auto;
	}
	.container-teams-date {
		display: flex;
		justify-content: space-between;
		margin-left: 25px;
	}
	.teams-date-container {
		display: flex;
		gap: 12px;
		align-items: center;
		position: relative;
	}
	.break {
		top: -30px;
		position: absolute;
	}
	.teams-date-time-container {
		display: flex;
		gap: 5px;
		align-items: center;
	}
	.teams {
		font: $h5-regular;
		color: $text-accent-blue;
	}
	.date {
		font: $h6-medium;
		max-width: 104px;
		text-align: center;
		margin-right: 21px;
	}
	.teams-date-score {
		font: $h4-medium;
		color: $text-dark;
	}
	.teams-date-time {
		color: #00fc76;
		font: $h4-regular;
	}
	.table-container-wrapper {
		overflow-x: auto;
	}
	.table-container {
		padding: 2px 15px 4px;
	}
	@supports (-moz-appearance: none) {
		.table-container {
			display: table;
		}
	}
	.table {
		display: grid;
		overflow: hidden;
		border-radius: 4px;
		border: 1px solid white;
		border-collapse: collapse;
		grid-template-columns: repeat(13, 1fr);
		text-align: center;
		white-space: nowrap;
		width: 756px;
		height: 70px;
		color: $text-dark;
		margin-right: 15px;
	}
	.first-row {
		padding: 7px;
		background: #d0eafa;
		font: normal 600 13px/120% 'Noto Sans', sans-serif;
		border-bottom: 1px solid #f2f2f2;
		border-right: 1px solid #f2f2f2;
	}
	:nth-last-child(1 of .first-row) {
		border-right: none;
	}
	.second-row {
		padding: 12px;
		border-right: 1px solid #f2f2f2;
		background: white;
		font: normal 400 13px/120% 'Noto Sans', sans-serif;
	}
	:nth-last-child(1 of .second-row) {
		border-right: none;
	}

	.accentField-green {
		background: #28995d;
		color: white;
	}
	.accentField-red {
		color: white;
		background: #9c202d;
	}
</style>
