<template>
	<section class="section5">
		<div class="title-area t-1">
			<h2>FAQ’S</h2>
			<h3>Trade Your questions for answers</h3>
		</div>
		<section class="faq-area f-1">
			<div
				class="faq-card"
				v-for="(faq, index) in faqs"
				:key="index"
				:class="{ expanded: faq.isOpen }"
			>
				<ul>
					<li>{{ faq.question }}</li>
					<li class="btn" @click="toggleFaq(index)">
						<img :src="faq.isOpen ? closeIcon : openIcon" alt="" />
					</li>
				</ul>
				<div>
					<p>
						{{ faq.answer }}
					</p>
				</div>
			</div>
		</section>
	</section>
</template>

<script setup>
import { ref, onMounted } from "vue";
import openIcon from "../assets/images/Cross.svg";
import closeIcon from "../assets/images/Close.svg";
import { gsap } from "gsap";
import ScrollTrigger from "gsap/ScrollTrigger";

gsap.registerPlugin(ScrollTrigger);

const faqs = ref([
	{
		question: "Who is Roost?",
		answer:
			"Make sure you download the Metamask Wallet app or browser extension for you phone. Simply purchase $ROOST using BASE-ETH through a DEX like Uniswap. Easy!",
		isOpen: false,
	},
	{
		question: "What chain is $roost on?",
		answer: "Your answer for second FAQ here",
		isOpen: false,
	},
	{
		question: "How can i buy $roost?",
		answer: "Your answer for third FAQ here",
		isOpen: false,
	},
]);

const toggleFaq = (index) => {
	faqs.value[index].isOpen = !faqs.value[index].isOpen;
};

onMounted(() => {
	gsap.from(".t-1", {
		scrollTrigger: {
			trigger: ".t-1",
			start: "top 80%",
			toggleActions: "play none none reverse",
		},
		scale: 0,
		duration: 1.2,
		opacity: 0,
		ease: "back.out(1.7)",
	});

	gsap.from(".f-1", {
		scrollTrigger: {
			trigger: ".f-1",
			start: "top 80%",
			toggleActions: "play none none reverse",
		},
		scale: 0,
		duration: 1.2,
		opacity: 0,
		ease: "back.out(1.7)",
	});
});
</script>

<style lang="scss" scoped>
@use "../styles/variables.scss" as *;
@use "../styles/mixin.scss" as *;

.section5 {
	background: #dae6ff;
	padding: 74px 118px;

	@include mobile {
		padding: 35px 23px;
	}
	@include tablet {
		padding: 35px 40px;
	}

	.title-area {
		text-align: center;

		h2 {
			font: 700 67px Font1;
			text-transform: uppercase;
			line-height: 74.29px;
			color: #3a80fe;
			text-shadow: 2px 2px 2px #000000;
			margin-bottom: 10px;

			@include mobile {
				font: 400 37px Font1;
				line-height: 42.29px;
			}
		}

		h3 {
			font: 700 48px Font1;
			text-transform: uppercase;
			line-height: 54.29px;
			color: #ffffff;
			text-shadow: 2px 2px 4px #000000;
			margin-bottom: 10px;
			width: 40%;
			margin: 0 auto;

			@include mobile {
				font: 400 25px Font1;
				line-height: 22.29px;
				width: 100%;
			}
			@include tablet {
				width: 100%;
			}
			@include macbook {
				width: 60%;
			}
		}
	}

	.faq-area {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
		margin-top: 64px;

		@include mobile {
			margin-top: 38px;
		}

		.faq-card {
			width: 872px;
			height: 67px;
			margin-bottom: 18px;
			padding: 0 14px 22px;
			background: #ffffff;
			border-radius: 10px;
			border: 2px solid #000000;
			box-shadow: 0px 4px rgba(0, 0, 0, 0.6);
			overflow: hidden;
			transition: height 0.3s ease;

			&.expanded {
				height: 150px;

				@include mobile {
					height: auto;
				}
			}

			@include mobile {
				width: 100%;
				padding: 0 10px 22px;
			}
			@include tablet {
				width: 100%;
			}

			ul {
				display: flex;
				justify-content: space-between;
				align-items: center;
				height: 67px;
				padding: 22px 0;
				margin-bottom: 16px;

				@include mobile {
					margin-bottom: 10px;
				}

				li {
					list-style: none;
					font: 400 21px Font1;
					text-transform: capitalize;
				}
				.btn {
					cursor: pointer;

					img {
						transition: transform 0.3s ease;

						.expanded & {
							transform: rotate(45deg);
						}
					}
				}
			}

			div {
				p {
					font: 400 16px Font2;
					color: #000000;
				}
			}
		}
	}
}
</style>
