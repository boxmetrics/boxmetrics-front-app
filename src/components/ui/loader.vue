<template>
	<div class="loader-container">
		<span class="loader">
			<svg
				:width="width"
				:height="height"
				viewBox="0 0 30 30"
				xmlns="http://www.w3.org/2000/svg"
				data-svg="spinner"
			>
				<circle
					fill="none"
					:stroke="strokeColor"
					cx="15"
					cy="15"
					r="14"
				></circle>
			</svg>
		</span>
	</div>
</template>
<script>
export default {
	name: "Loader",
	props: {
		strokeColor: {
			type: String,
			default: "#ffffff"
		},
		width: {
			type: String,
			default: "20"
		},
		height: {
			type: String,
			default: "20"
		}
	}
};
</script>

<style lang="scss" scoped>
.loader {
	width: 100%;
	height: 100%;
	display: flex;
	align-items: center;
	justify-content: center;
	z-index: 100;
	> * {
		animation: rotate 1.4s linear infinite;
	}
	> * > * {
		stroke-dasharray: 88px;
		stroke-dashoffset: 0;
		transform-origin: center;
		animation: spinner 1.4s ease-in-out infinite;
		animation-name: spinner;
		animation-duration: 1.4s;
		animation-timing-function: ease-in-out;
		animation-delay: 0s;
		animation-iteration-count: infinite;
		animation-direction: normal;
		animation-fill-mode: none;
		animation-play-state: running;
		stroke-width: 2;
		stroke-linecap: round;
		position: relative;
	}
}
</style>
