<template>
	<section>
		<ul ref="ticker">
			<li>$ROOST</li>
			<li>#</li>
			<li>$ROOST</li>
			<li>#</li>
			<li>$ROOST</li>
			<li>#</li>
			<li>$ROOST</li>
			<li>#</li>
			<li>$ROOST</li>
			<li>#</li>
			<li>$ROOST</li>
			<li>#</li>
			<li>$ROOST</li>
			<li>#</li>
			<li>$ROOST</li>
			<li>#</li>
			<li>$ROOST</li>
			<li>#</li>
			<li>$ROOST</li>
			<li>#</li>
			<li>$ROOST</li>
			<li>#</li>
			<li>$ROOST</li>
			<li>#</li>
			<li>$ROOST</li>
			<li>#</li>
			<li>$ROOST</li>
			<li>#</li>
			<li>$ROOST</li>
			<li>#</li>
			<li>$ROOST</li>
			<li>#</li>
			<li>$ROOST</li>
			<li>#</li>
			<li>$ROOST</li>
			<li>#</li>
		</ul>
	</section>
</template>

<script setup>
import { ref, onMounted } from "vue";
import { gsap } from "gsap";

const ticker = ref(null);

onMounted(() => {
	const endlessAnimation = gsap.to(ticker.value, {
		duration: 15,
		x: "-40%",
		ease: "linear",
		repeat: -1,
	});
});
</script>

<style lang="scss" scoped>
section {
	padding: 27px 37px;
	background: #ffa85a;
	overflow-x: hidden;
	ul {
		display: flex;
		align-items: center;
		gap: 3em;
		white-space: nowrap;

		li {
			list-style: none;
			font: 700 22px Font3;
		}
	}
}
</style>
