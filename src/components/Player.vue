<template>
	<div class="player">
		<player-button :playing="playing" @click.native="togglePlay"></player-button>
		<player-bar :progress="progress"></player-bar>
	</div>
</template>

<script>
import PlayerButton from './PlayerButton.vue';
import PlayerBar from './PlayerBar.vue';
import { Howl, Howler } from 'howler';

const sound = new Howl({
	src: ['/dolores/static/teaser.mp3']
});
sound.fade(0, 1, 1000);

export default {
	name: 'Player',
	components: {
		PlayerButton,
		PlayerBar
	},
	data() {
		return {
			playing: false,
			progress: 0
		};
	},
	watch: {
		playing(val) {
			if (val) {
				sound.play();
				requestAnimationFrame(this.step);
			}
			else sound.pause();
		}
	},
	computed: {},
	methods: {
		togglePlay() {
			this.playing = !this.playing;
		},
		step() {
			// Determine our current seek position.
			let seek = sound.seek();
			this.progress = Math.round(seek / sound.duration() * 320);

			// If the sound is still playing, continue stepping.
			if (sound.playing()) {
				requestAnimationFrame(this.step);
			}
		}
	},
	created() {
		sound.on('end', () => {
			this.playing = false;
		});
	}
};
</script>

<style lang="scss">
.player {
	position: relative;
	height: 320px;
	display: flex;
	justify-content: center;
	align-items: center;
	background-image: linear-gradient(
			to right,
			rgba(0, 0, 0, 0.5) 0%,
			rgba(0, 0, 0, 0.5) 100%
		),
		url('/dolores/static/cover.jpg');
	background-size: cover;
}
</style>
