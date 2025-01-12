<template>
	<Navbar />
	<Section1 />
	<Section2 />
	<Section3 />
	<Section4 />
	<Section2 />
	<Section5 />
	<Section6 />
</template>

<script setup>
import Navbar from "../components/Navigation.vue";
import Section1 from "../components/Section1.vue";
import Section2 from "../components/Section2.vue";
import Section3 from "../components/Section3.vue";
import Section4 from "../components/Section4.vue";
import Section5 from "../components/Section5.vue";
import Section6 from "../components/Section6.vue";
</script>

<style lang="scss">
@use "../styles/main.scss" as *;
</style>
