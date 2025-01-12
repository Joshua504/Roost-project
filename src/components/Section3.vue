<template>
	<section class="section3">
		<div class="text-area2">
			<h2>roost 101</h2>
			<p>
				$roost is on
				<span><img src="../assets/images/Base.svg" alt="" /> base</span>
			</p>
		</div>
		<img class="nest" src="../assets/images/Nest.svg" alt="" />
		<section class="cards-area">
			<div class="card c-1">
				<img src="../assets/images/Egg-1.svg" alt="" />
				<h3>add base meta mask</h3>
				<p>
					Download & install the Metamask Wallet either from the app store on
					your phone or the browser extension for desktop
				</p>
			</div>
			<div class="card c-2">
				<img src="../assets/images/Egg-2.svg" alt="" />
				<h3>load up eth</h3>
				<p>
					Head over to bridge.base.org, connect your wallet on the Ethereum
					blockchain. Choose how much ETH you would like to bridge from the
					erc20 network to Base.
				</p>
			</div>
			<div class="card c-3">
				<img src="../assets/images/Egg-3.svg" alt="" />
				<h3>buy $roost</h3>
				<p>
					Head over to Uniswap and paste the $ROOST contract Address listed on
					this website to swap your ETH.
				</p>
			</div>
			<div class="card c-4">
				<img src="../assets/images/Egg-4.svg" alt="" />
				<h3>add $roost to your</h3>
				<p>
					Now all you have to do is add the $ROOST contract address to your
					Metamask Wallet for your $ROOST tokens to show. Welcome aboard!
				</p>
			</div>
		</section>
		<div class="img-area">
			<div class="n-1"><Section7 /></div>
			<div>
				<img class="pol" src="../assets/images/Poultry.svg" alt="" />
			</div>
		</div>
	</section>
</template>

<script setup>
import Section7 from "../components/Eggnest.vue";
import { ref, onMounted } from "vue";
import { gsap } from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);

onMounted(() => {
	gsap.from(".text-area2", {
		scrollTrigger: {
			trigger: ".text-area2",
			start: "top 80%",
			toggleActions: "play none none reverse",
		},
		scale: 0,
		duration: 1.2,
		opacity: 0,
		ease: "back.out(1.7)",
	});

	const cards = [
		{ selector: ".c-1", start: "80%", xOffset: -100 },
		{ selector: ".c-2", start: "80%", xOffset: 100 },
		{ selector: ".c-3", start: "80%", xOffset: -100 },
		{ selector: ".c-4", start: "80%", xOffset: 100 },
	];

	cards.forEach(({ selector, start, xOffset }) => {
		gsap.from(selector, {
			scrollTrigger: {
				trigger: selector,
				start: `top ${start}`,
				toggleActions: "play none none reverse",
			},
			x: xOffset,
			duration: 1,
			opacity: 0,
			ease: "power2.out",
		});
	});
});
</script>

<style lang="scss" scoped>
@use "../styles/variables.scss" as *;
@use "../styles/mixin.scss" as *;

.section3 {
	padding: 113px 0px 0;
	background: #dae6ffba;
	position: relative;
	overflow: hidden;

	@include mobile {
		padding: 70px 0 0;
	}

	.text-area2 {
		text-align: center;
		margin-bottom: 104px;

		@include mobile {
			margin-bottom: 50px;
		}

		h2 {
			font: 700 67px Font1;
			text-transform: uppercase;
			line-height: 74.29px;
			color: #3a80fe;
			text-shadow: 2px 4px 4px #000000;

			@include mobile {
				font: 400 37px Font1;
				line-height: 42.29px;
			}
		}
		p {
			font: 400 21px Font1;
			text-transform: uppercase;
			line-height: 23.29px;
			color: #000000;
			display: flex;
			justify-content: center;
			align-items: center;
			gap: 10px;

			@include mobile {
				font: 400 14px Font1;
				line-height: 42.29px;
			}

			span {
				color: #3a80fe;
				font: 400 19px Font2;
				line-height: 19px;
				display: flex;
				justify-content: center;
				align-items: center;
				gap: 5px;

				@include mobile {
					font: 400 14px Font2;
					line-height: 42.29px;
				}
			}
		}
	}

	.nest {
		position: absolute;
		left: 50%;
		top: 45%;
		transform: translate(-50%, -50%);
		z-index: -1;

		@include mobile {
			width: 100%;
			top: 26%;
		}
		@include tablet {
			width: 100%;
			top: 40%;
		}
	}

	.cards-area {
		display: grid;
		grid-template-columns: repeat(2, 1fr);
		justify-items: center;
		column-gap: 38px;
		row-gap: 65px;
		margin-bottom: 10rem;

		@include mobile {
			grid-template-columns: 1fr;
			column-gap: 0;
			row-gap: 50px;
			padding: 0 23px;
			margin-bottom: 0;
		}
		@include tablet {
			grid-template-columns: 1fr;
			column-gap: 0;
			row-gap: 50px;
			padding: 0 23px;
			margin-bottom: 0;
		}

		.card {
			width: 481.87px;
			height: 220px;
			padding: 38px 20px;
			background: #3a80fe;
			border: 1px solid #000000;
			border-radius: 20px;
			box-shadow: rgba(0, 0, 0, 0.6) 1.95px 1.95px 2.6px;
			position: relative;

			@include mobile {
				width: 100%;
				height: 154px;
			}
			@include tablet {
				width: 100%;
				// height: 154px;
			}

			img {
				position: absolute;
				left: 10px;
				top: -45px;

				@include mobile {
					width: 50px;
					top: -35px;
				}
			}

			h3 {
				font: 400 35px Font1;
				text-transform: uppercase;
				color: #ffffff;
				margin-bottom: 10px;

				@include mobile {
					font: 400 24px Font1;
					line-height: 23.29px;
				}
			}

			p {
				font: 400 20px Font2;
				text-transform: capitalize;
				color: #ffffff;
				margin-bottom: 16px;

				@include mobile {
					font: 400 14px Font2;
				}
			}
		}

		.c-1 {
			grid-column: 1;
			grid-row: 1;
			justify-self: end;

			@include mobile {
				grid-column: 1;
				justify-self: center;
			}
			@include tablet {
				grid-column: 1;
				justify-self: center;
			}
		}

		.c-2 {
			grid-column: 2;
			justify-self: start;
			transform: translateY(60%);

			@include mobile {
				grid-column: 1;
				justify-self: center;
				transform: translateY(0%);
			}
			@include tablet {
				grid-column: 1;
				justify-self: center;
				transform: translateY(0%);
			}
		}
		.c-3 {
			grid-column: 1;
			justify-self: end;

			@include mobile {
				grid-column: 1;
				justify-self: center;
			}
			@include tablet {
				grid-column: 1;
				justify-self: center;
			}
		}
		.c-4 {
			grid-column: 2;
			justify-self: start;
			transform: translateY(60%);

			@include mobile {
				grid-column: 1;
				justify-self: center;
				transform: translateY(0%);
			}
			@include tablet {
				grid-column: 1;
				justify-self: center;
				transform: translateY(0%);
			}
		}
	}

	.img-area {
		height: 650px;
		position: relative;
		padding-top: 140px;
		display: flex;
		justify-content: center;
		align-items: center;
		background: linear-gradient(to bottom, transparent 70%, #a5ef79 50%);
		background-position: 0 20;

		@include mobile {
			height: 300px;
			padding-top: 30px;
		}

		.n-1 {
			position: absolute;
			left: 61%;
			bottom: 10%;

			@include macbook {
				left: 66%;
			}
			@include mobile {
				left: 74%;
				bottom: 15%;
			}
			@include tablet {
				left: 71%;
			}
		}

		.pol {
			@include mobile {
				width: 100%;
			}
			@include tablet {
				width: 100%;
			}
		}
	}
}
</style>
