<template>
	<div class="player-bar" :style="{ width: progress + 'px'}">
		&nbsp;
	</div>
</template>

<script>
export default {
	name: 'PlayerBar',
	props: {
		progress: Number
	}
};
</script>

<style lang="scss">
.player-bar {
	display: block;
	background-color: slateblue;
	width: 0;
	height: 5px;
	bottom: 0;
	left:0;
	position: absolute;
}
</style>
