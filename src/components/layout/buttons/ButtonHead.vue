<script setup>
const props = defineProps({
    type: {
        type: String,
        default: 'primary'
    },
    className: {
        type: String
    },
    text: {
        type: String
    }
})
</script>
<template>
    <button :class="['btn', `btn_${type}`, className]">
        <span v-if="text">{{ text }}</span>
        <span v-else>Registration</span>
    </button>
</template>

<style lang="scss" scoped>
@import "@/styles/global";
.btn{
    width: 101px;
    height: 33px;
    border: none;
    padding: 7px 7px 8px 11px;
    font: $h5-medium;
    &_primary{
        color: white;
        background: url('data:image/svg+xml,<svg width="101" height="33" viewBox="0 0 101 33" fill="none" xmlns="http://www.w3.org/2000/svg"><path d="M0.5 6C0.5 2.96243 2.96243 0.5 6 0.5H94C97.0376 0.5 99.5 2.96243 99.5 6V18.5961C99.5 20.0105 98.9551 21.3705 97.9785 22.3937L90.911 29.7976C89.8732 30.8849 88.4357 31.5 86.9326 31.5H6C2.96244 31.5 0.5 29.0376 0.5 26V6Z" fill="url(%23paint0_linear_3123_1411)" stroke="url(%23paint1_linear_3123_1411)"/><path d="M100 31V27.4142C100 26.5233 98.9229 26.0771 98.2929 26.7071L94.7071 30.2929C94.0771 30.9229 94.5233 32 95.4142 32H99C99.5523 32 100 31.5523 100 31Z" fill="%233097C0" stroke="%2346F4FF"/><defs><linearGradient id="paint0_linear_3123_1411" x1="57.5362" y1="32" x2="57.5362" y2="4.71616e-07" gradientUnits="userSpaceOnUse"><stop stop-color="%23248DB6"/><stop offset="1" stop-color="%237DD9FF"/></linearGradient><linearGradient id="paint1_linear_3123_1411" x1="85.5" y1="30" x2="30.7509" y2="-1.31288" gradientUnits="userSpaceOnUse"><stop stop-color="%2346F4FF"/><stop offset="1" stop-color="%232991BA" stop-opacity="0"/></linearGradient></defs></svg>');
        filter: drop-shadow(2px 2px 4px rgba(100, 210, 255, 0.44)) drop-shadow(0 2px 2px rgba(0, 0, 0, 0.12));
        &-disabled{
            display: none;
        }
    }   
    &_secondary{
        color: $text-accent-blue;
        background: url('data:image/svg+xml,<svg width="109" height="41" viewBox="0 0 109 41" fill="none" xmlns="http://www.w3.org/2000/svg"><g filter="url(%23filter0_dd_2163_23192)"><path d="M2 8C2 4.68629 4.68629 2 8 2H96C99.3137 2 102 4.68629 102 8V20.5961C102 22.1391 101.406 23.6228 100.34 24.7389L93.2727 32.1429C92.1406 33.3289 90.5723 34 88.9326 34H8C4.68629 34 2 31.3137 2 28V8Z" fill="white"/><path d="M8 2.5H96C99.0376 2.5 101.5 4.96243 101.5 8V20.5961C101.5 22.0105 100.955 23.3705 99.9785 24.3937L92.911 31.7976C91.8732 32.8849 90.4357 33.5 88.9326 33.5H8C4.96244 33.5 2.5 31.0376 2.5 28V8C2.5 4.96243 4.96243 2.5 8 2.5Z" stroke="url(%23paint0_linear_2163_23192)"/></g><g filter="url(%23filter1_dd_2163_23192)"><path d="M102 33V29.4142C102 28.5233 100.923 28.0771 100.293 28.7071L96.7071 32.2929C96.0771 32.9229 96.5233 34 97.4142 34H101C101.552 34 102 33.5523 102 33Z" fill="white"/><path d="M102 33V29.4142C102 28.5233 100.923 28.0771 100.293 28.7071L96.7071 32.2929C96.0771 32.9229 96.5233 34 97.4142 34H101C101.552 34 102 33.5523 102 33Z" stroke="%2346F4FF"/></g><defs><filter id="filter0_dd_2163_23192" x="0" y="0" width="108" height="40" filterUnits="userSpaceOnUse" color-interpolation-filters="sRGB"><feFlood flood-opacity="0" result="BackgroundImageFix"/><feColorMatrix in="SourceAlpha" type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0" result="hardAlpha"/><feOffset dx="2" dy="2"/><feGaussianBlur stdDeviation="2"/><feComposite in2="hardAlpha" operator="out"/><feColorMatrix type="matrix" values="0 0 0 0 0.391667 0 0 0 0 0.823537 0 0 0 0 1 0 0 0 0.44 0"/><feBlend mode="normal" in2="BackgroundImageFix" result="effect1_dropShadow_2163_23192"/><feColorMatrix in="SourceAlpha" type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0" result="hardAlpha"/><feOffset dy="2"/><feGaussianBlur stdDeviation="1"/><feComposite in2="hardAlpha" operator="out"/><feColorMatrix type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0.12 0"/><feBlend mode="normal" in2="effect1_dropShadow_2163_23192" result="effect2_dropShadow_2163_23192"/><feBlend mode="normal" in="SourceGraphic" in2="effect2_dropShadow_2163_23192" result="shape"/></filter><filter id="filter1_dd_2163_23192" x="93.9111" y="25.9112" width="14.5889" height="14.5888" filterUnits="userSpaceOnUse" color-interpolation-filters="sRGB"><feFlood flood-opacity="0" result="BackgroundImageFix"/><feColorMatrix in="SourceAlpha" type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0" result="hardAlpha"/><feOffset dx="2" dy="2"/><feGaussianBlur stdDeviation="2"/><feComposite in2="hardAlpha" operator="out"/><feColorMatrix type="matrix" values="0 0 0 0 0.391667 0 0 0 0 0.823537 0 0 0 0 1 0 0 0 0.44 0"/><feBlend mode="normal" in2="BackgroundImageFix" result="effect1_dropShadow_2163_23192"/><feColorMatrix in="SourceAlpha" type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 127 0" result="hardAlpha"/><feOffset dy="2"/><feGaussianBlur stdDeviation="1"/><feComposite in2="hardAlpha" operator="out"/><feColorMatrix type="matrix" values="0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0.12 0"/><feBlend mode="normal" in2="effect1_dropShadow_2163_23192" result="effect2_dropShadow_2163_23192"/><feBlend mode="normal" in="SourceGraphic" in2="effect2_dropShadow_2163_23192" result="shape"/></filter><linearGradient id="paint0_linear_2163_23192" x1="87.5" y1="32" x2="32.7509" y2="0.687118" gradientUnits="userSpaceOnUse"><stop stop-color="%2346F4FF"/><stop offset="1" stop-color="%232991BA" stop-opacity="0"/></linearGradient></defs></svg>');
        filter: drop-shadow(2px 2px 4px rgba(100, 210, 255, 0.44)) drop-shadow(0 2px 2px rgba(0, 0, 0, 0.12));
        &-disabled{
            display: none;
        }
    }
}
</style>