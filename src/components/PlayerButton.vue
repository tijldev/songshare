<template>
	<div class='player-button'>
		<div class="player-button-play" v-if="!playing">&nbsp;</div>
		<div class="player-button-pause" v-if="playing">&nbsp;</div>
	</div>
</template>

<script>
export default {
	name: 'PlayerButton',
	props: {
		playing: Boolean
	}
};
</script>

<style lang="scss">
.player-button {
	display: flex;
	align-items: center;
	justify-content: center;
	width: 50px;
	height: 50px;
	border: 2px solid white;
	border-radius: 50%;

	&:hover {
		cursor: pointer;
	}
}

.player-button-play {
	width: 0;
	height: 0;
	border-style: solid;
	border-width: 12px 0 12px 20px;
	border-color: transparent transparent transparent white;
	margin-left: 4px;
}

.player-button-pause {
	width: 15px;
	height: 20px;
	box-sizing: border-box;
	border-style: solid;
	border-width: 0px 5px 0px 5px;
	border-color: white;
}
</style>
