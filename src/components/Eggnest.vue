<template>
	<section class="Egg-nest">
		<div class="egg e-1">
			<a href=""><img src="../assets/images/E-tel.svg" alt="" /></a>
		</div>
		<div class="egg e-2">
			<a href=""><img src="../assets/images/E-twi.svg" alt="" /></a>
		</div>
		<div class="nest"><img src="../assets/images/E-nest.svg" alt="" /></div>
	</section>
</template>

<script setup></script>

<style lang="scss" scoped>
@use "../styles/variables.scss" as *;
@use "../styles/mixin.scss" as *;

.Egg-nest {
	position: relative;

	.egg {
		position: absolute;
		transition: all 0.3s ease;

		@include mobile {
			width: 30%;

			img {
				width: 100%;
			}
		}

		&:hover {
			animation: shake 0.5s ease-in-out infinite;
		}
	}
	.e-1 {
		top: -1.2em;
		left: 2em;
		z-index: 1;

		@include mobile {
			top: -0.8em;
			left: 0.5em;
		}
	}
	.e-2 {
		top: -1.3em;
		left: 5.8em;

		@include mobile {
			top: -0.7em;
			left: 1.9em;

			img {
				width: 70%;
			}
		}
	}

	.nest {
		@include mobile {
			width: 60%;

			img {
				width: 100%;
			}
		}
	}
}
@keyframes shake {
	0% {
		transform: rotate(0deg);
	}
	25% {
		transform: rotate(-5deg);
	}
	50% {
		transform: rotate(5deg);
	}
	75% {
		transform: rotate(-5deg);
	}
	100% {
		transform: rotate(0deg);
	}
}
</style>
