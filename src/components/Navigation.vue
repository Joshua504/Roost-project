<template>
	<nav>
		<div class="logo">
			<router-link to="/"
				><img src="../assets/images/Logo.svg" alt=""
			/></router-link>
			<div
				class="hamburger"
				:class="{ 'is-active': isOpen }"
				@click="toggleMenu"
			>
				<span class="bars"></span>
				<span class="bars"></span>
				<span class="bars"></span>
			</div>
		</div>
		<section class="nav-area" :class="{ active: isOpen }">
			<ul>
				<router-link class="link" to="/">
					<li @click="closeMenu">home</li>
				</router-link>
				<router-link class="link" to="/">
					<li @click="closeMenu">about us</li>
				</router-link>
				<router-link class="link" to="/">
					<li @click="closeMenu">roadmap</li>
				</router-link>
				<router-link class="link" to="/">
					<li @click="closeMenu">tokenomics</li>
				</router-link>
				<router-link class="link" to="/">
					<li @click="closeMenu">join community</li>
				</router-link>
			</ul>
			<div><button @click="closeMenu">presale</button></div>
		</section>
	</nav>
</template>

<script setup>
import {ref} from 'vue'
const isOpen = ref(false);

const toggleMenu = () => {
	isOpen.value = !isOpen.value;
};
const closeMenu = () => {
	isOpen.value = false;
};
</script>

<style lang="scss">
@use "../styles/variables.scss" as *;
@use "../styles/mixin.scss" as *;
@use "sass:color" as color;

nav {
	position: fixed;
	width: 100%;
	top: 0;
	display: flex;
	align-items: center;
	padding: 28px 118px;
	background: #fff6b5;
	z-index: 10;
	border-bottom: 1px solid #000000;

	@include mobile {
		padding: 15px;
		border-bottom: 2px solid #000000;
	}
	@include tablet {
		padding: 15px;
		border-bottom: 2px solid #000000;
	}

	.logo {
		display: flex;
		align-items: center;
		gap: 1em;
		width: 925px;

		@include mobile {
			width: 100%;
			justify-content: space-between;
		}
		@include tablet {
			width: 100%;
			justify-content: space-between;
		}
		@include macbook {
			width: 400px;
			justify-content: space-between;
		}

		.hamburger {
			display: none;
			flex-direction: column;
			padding: 5px;
			gap: 0.5em;
			justify-content: space-between;
			cursor: pointer;

			@include mobile {
				display: block;
			}
			@include tablet {
				display: block;
			}
		}
		.bars {
			display: block;
			width: 30px;
			height: 4px;
			background: #000000;
			border-radius: 50px;
			transition: all 0.3s ease;
		}

		.bars:nth-child(1) {
			margin-bottom: 4px;
		}
		.bars:nth-child(2) {
			margin-bottom: 4px;
		}

		& .is-active {
			span:nth-child(1) {
				transform: rotate(45deg) translate(4px, 8px);
			}
			span:nth-child(2) {
				opacity: 0;
			}
			span:nth-child(3) {
				transform: rotate(-45deg) translate(4px, -8px);
			}
		}
	}

	.nav-area {
		display: flex;
		align-items: center;
		justify-content: space-between;
		width: 100%;

		@include mobile {
			position: absolute;
			flex-direction: column;
			right: 0;
			top: -400%;
			align-items: center;
			background: #508efe;
			width: 100%;
			padding: 1em;
			height: auto;
			transition: right 0.3s ease-in-out;
			gap: 20px;
			padding: 1em;
			border-bottom-right-radius: 10px;
			border-bottom-left-radius: 10px;

			&.active {
				top: 103%;
			}
		}
		@include tablet {
			position: absolute;
			flex-direction: column;
			right: 0%;
			top: -400%;
			align-items: center;
			background: #508efe;
			width: 100%;
			padding: 1em;
			height: auto;
			gap: 20px;
			padding: 1em;
			border-bottom-right-radius: 10px;
			border-bottom-left-radius: 10px;

			transition: right 0.3s ease-in-out;

			&.active {
				top: 103%;
			}
		}

		ul {
			display: flex;
			gap: 22px;
			align-items: center;

			@include mobile {
				flex-direction: column;
				gap: 15px;
				width: 100%;
				align-items: center;
			}
			@include tablet {
				flex-direction: column;
				gap: 15px;
				width: 100%;
				align-items: center;
			}

			.link {
				text-decoration: none;

				li {
					list-style: none;
					text-transform: capitalize;
					font: 700 16px Font3;
					color: #000000;
				}
			}
		}

		button {
			padding: 10px 22px;
			font: 700 16px Font3;
			color: #ffffff;
			text-transform: uppercase;
			outline: transparent;
			border: 2px solid #000000;
			border-radius: 10px;
			background: #508efe;
			cursor: pointer;
			box-shadow: 0px 4px rgba(0, 0, 0, 0.6);
			transition: all 0.3s ease-in-out;

			&:hover {
				box-shadow: 0px 0px rgba(0, 0, 0, 0.6);
				background: color.scale(#508efe, $lightness: -20%);
			}

			@include mobile {
				// display: none;
			}
		}
	}
}
</style>
