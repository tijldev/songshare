<template>
  <a :href="link.url" target="_blank" class="service-link">
    <img class="link-image" :src="info.image" />
    <span class="button">{{ info.linktext }}</span>
  </a>
</template>

<script>
const services = {
	spotify: {
		name: 'Spotify',
		image: './static/logos/spotify.svg',
		linktext: 'Listen'
	},
	deezer: {
		name: 'Deezer',
		image: './static/logos/deezer.svg',
		linktext: 'Listen'
	},
	'google-play': {
		name: 'Google Play',
		image: './static/logos/google-play.svg',
		linktext: 'Download'
	},
		'apple-music': {
		name: 'Apple Music',
		image: './static/logos/apple-music.svg',
		linktext: 'Listen'
	},
		itunes: {
		name: 'iTunes',
		image: './static/logos/itunes.svg',
		linktext: 'Download'
	},
		tidal: {
		name: 'Tidal',
		image: './static/logos/tidal.svg',
		linktext: 'Listen'
	}
};

export default {
	name: 'ServiceLink',
	props: {
		link: Object
	},
	computed: {
		info() {
			return services[this.link.service];
		}
	}
};
</script>

<style lang="scss">
.service-link {
	display: flex;
	align-items: center;
	justify-content: space-between;
	text-decoration: none;
	padding: 20px;
	transition: background-color 0.2s linear;
	border-bottom: 1px solid rgb(240,240,240);
}

.service-link:hover {
	background-color: whitesmoke;

	.button {
		color: white;
		background-color: darkslategrey;
	}
}

.link-image {
	max-width: 125px;
	max-height: 40px;
}

.button {
	color: black;
	padding: 10px;
	border: 1px solid darkslategray;
	border-radius: 5px;
	transition: background-color 0.2s linear, color 0.2s linear;
}
</style>
