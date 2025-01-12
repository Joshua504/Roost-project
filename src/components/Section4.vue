<template>
	<section class="section4">
		<div class="title-area1">
			<h2>TOKENOMICS</h2>
			<h3>Supply Breakdown</h3>
			<p>Total Supply: 1 Billion Tokens</p>
		</div>
		<div class="flex-area">
			<section class="card-area">
				<div class="card a-1">
					<h3>10% Marketing</h3>
					<ul>
						<li>5% strategic partnership</li>
						<li>5% Advertisement</li>
					</ul>
				</div>
				<div class="card a-2">
					<h3>50% of Supply presale participant</h3>
					<ul>
						<li>15% Of Supply to LP</li>
					</ul>
				</div>
			</section>
			<div class="wood"><img src="../assets/images/Wood.svg" alt="" /></div>
			<section class="card-area area-2">
				<div class="card a-3">
					<h3>10% Team/Adviseors</h3>
					<ul>
						<li>5% Team (vested for 1 year)</li>
						<li>5% Advisors</li>
					</ul>
				</div>
				<div class="card a-4">
					<h3>15% Of Tokens for Exchanges</h3>
					<ul>
						<li>10% for CEX</li>
						<li>5% for market Making</li>
					</ul>
				</div>
			</section>
		</div>
	</section>
</template>

<script setup>
import { ref, onMounted } from "vue";
import { gsap } from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);

onMounted(() => {
	gsap.from(".title-area1", {
		scrollTrigger: {
			trigger: ".title-area1",
			start: "top 80%",
			toggleActions: "play none none reverse",
		},
		scale: 0,
		duration: 1.2,
		opacity: 0,
		ease: "back.out(1.7)",
	});

	const card = [
		{ selector: ".a-1", start: "80%", xOffset: 100 },
		{ selector: ".a-2", start: "80%", xOffset: -100 },
		{ selector: ".a-3", start: "80%", xOffset: 100 },
		{ selector: ".a-4", start: "80%", xOffset: -100 },
	];

	card.forEach(({ selector, start, xOffset }) => {
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

.section4 {
	padding: 50px 118px;
	background: #fff6b5;

	@include mobile {
		padding: 35px 23px;
	}
	@include tablet {
		padding: 35px 40px;
	}

	.title-area1 {
		text-align: center;

		h2 {
			font: 700 67px Font1;
			text-transform: uppercase;
			line-height: 74.29px;
			color: #3a80fe;
			text-shadow: 2px 4px 4px #000000;
			margin-bottom: 10px;

			@include mobile {
				font: 400 37px Font1;
				line-height: 32.29px;
				margin-bottom: 8px;
			}
		}

		h3 {
			font: 400 24px Font1;
			text-transform: uppercase;
			line-height: 23.29px;
			color: #3a80fe;
			text-shadow: 2px 4px 4px #000000;
			margin-bottom: 8px;

			@include mobile {
				font: 400 16px Font1;
				line-height: 22.29px;
				margin-bottom: 3px;
			}
		}

		p {
			font: 400 16px Font2;
			line-height: 19px;

			@include mobile {
				font: 400 14px Font2;
			}
		}
	}

	.flex-area {
		position: relative;
		margin-top: 200px;
		display: flex;
		justify-content: space-between;
		flex-direction: column;
		gap: 30em;
		overflow: hidden;

		@include mobile {
			margin-top: 40px;
			gap: 20em;
			justify-content: center;
		}
		@include tablet {
			margin-top: 40px;
			gap: 20em;
			justify-content: center;
		}

		.wood {
			position: absolute;
			left: 50%;
			width: 50%;
			top: 45%;
			transform: translate(-50%, -50%);

			@include mobile {
				width: 100%;
				top: 48%;
				left: 45%;
			}

			img {
				width: 100%;
			}
		}

		.card-area {
			display: flex;
			justify-content: space-between;

			@include mobile {
				flex-direction: column;
				gap: 2em;
			}

			.card {
				@include mobile {
					text-align: center;
				}
				h3 {
					font: 500 21px Font2;
					margin-bottom: 8px;
				}
				li {
					font: 400 18px Font2;

					@include mobile {
						list-style: none;
					}
				}
			}
		}

		.area-2 {
			justify-self: end;
		}
	}
}
</style>
