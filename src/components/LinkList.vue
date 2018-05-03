<template>
	<div class="link-list">
		<div class="list-header">
			<h2>{{ artist }} - {{ title }}</h2>
			<p>Choose music service</p>
		</div>
		<service-link v-for="(link, index) in links" :key="index" :link="link"></service-link>
	</div>
</template>

<script>
import ServiceLink from './ServiceLink';

export default {
	name: 'LinkList',
	components: {
		ServiceLink
	},
	props: {
		links: Array,
		title: String,
		artist: String
	}
};
</script>

<style lang="scss">
.link-list {
	background-color: white;
}

.list-header {
	background: darkslategrey;
	color: white;
	height: 80px;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	position: relative;

	h2,
	p {
		margin: 3px;
	}

	&::after {
		content: '';
		width: 0;
		height: 0;
		border-left: 10px solid transparent;
		border-right: 10px solid transparent;
		border-top: 10px solid darkslategrey;
		position: absolute;
		bottom: -10px;
	}
}
</style>
