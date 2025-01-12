<template>
	<section class="section6">
		<div class="text-area">
			<h2>Socials</h2>
			<p>join the $roost community</p>
			<div class="btn-area">
				<button class="btn1">Buy $Roost</button>
				<button class="btn2">
					<img src="../assets/images/token_sdex.svg" alt="" />DEX TOOL
				</button>
			</div>
		</div>
		<div class="logo-area">
			<img src="../assets/images/LogoII.svg" alt="" />
			<section class="socials-area">
				<div><img src="../assets/images/TelegramII.svg" alt="" /></div>
				<div><img src="../assets/images/Twitter.svg" alt="" /></div>
			</section>
		</div>
	</section>
</template>

<script setup></script>

<style lang="scss" scoped>
@use "../styles/variables.scss" as *;
@use "../styles/mixin.scss" as *;
@use "sass:color" as color;

.section6 {
	position: relative;
	height: 500px;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	background-image: url("../assets/images/Footer.svg");
	background-repeat: no-repeat;
	background-size: cover;
	gap: 33px;
	padding: 74px 118px;

	@include mobile {
		padding: 35px 23px;
	}

	.text-area {
		text-align: center;

		h2 {
			font: 400 84px Font1;
			text-transform: uppercase;
			line-height: 94.29px;
			color: #ffffff;
			text-shadow: 2px 2px 2px #000000;
			margin-bottom: 10px;

			@include mobile {
				font: 400 54px Font1;
				line-height: 60.29px;
			}
		}

		p {
			font: 400 25px Font1;
			text-transform: uppercase;
			line-height: 27.29px;
			color: #ffffff;

			@include mobile {
				font: 400 19px Font1;
				line-height: 21.29px;
			}
		}

		.btn-area {
			display: flex;
			gap: 2em;
			margin-top: 28px;

			@include mobile {
				gap: 1em;
			}

			button {
				font: 400 20px Font3;
				text-transform: uppercase;
				padding: 10px 40px;
				border-radius: 10px;
				border: 2px solid #000000;
				box-shadow: 0px 4px rgba(0, 0, 0, 0.6);
				transition: all 0.3s ease-in-out;

				@include mobile {
					font: 400 14px "Font1";
					text-align: center;
					padding: 10px 20px;
				}
			}

			.btn1 {
				background: #3a80fe;
				color: #ffffff;

				&:hover {
					box-shadow: 0px 0px rgba(0, 0, 0, 0.6);
					background: #ff9d46;
					color: #000000;
				}
			}

			.btn2 {
				background: transparent;
				color: #000000;
				display: flex;
				justify-content: center;
				gap: 5px;
				align-items: center;
				background: #fff297;

				&:hover {
					box-shadow: 0px 0px rgba(0, 0, 0, 0.6);
					background: #ff9d46;
				}
			}
		}
	}

	.logo-area {
		display: flex;
		justify-content: center;
		align-items: center;

		@include mobile {
			position: relative;
			flex-direction: column-reverse;
			gap: 1em;
		}
		@include tablet {
			position: relative;
			flex-direction: column-reverse;
			gap: 1em;
		}

		.socials-area {
			display: flex;
			align-items: center;
			gap: 1em;
			position: absolute;
			right: 118px;

			@include mobile {
				position: relative;
				right: 0;
			}
			@include tablet {
				position: relative;
				right: 0;
			}

			div {
				padding: 1em;
				display: flex;
				justify-content: center;
				align-items: center;
				background: #3a80fe;
				border: 2px solid #ffffff;
				box-shadow: 0px 4px rgba(255, 255, 255, 0.6);
				border-radius: 10px;
				cursor: pointer;
				transition: box-shadow 0.3s ease;

				&:hover {
					box-shadow: 0px 0px rgba(0, 0, 0, 0.6);
				}
			}
		}
	}
}
</style>
