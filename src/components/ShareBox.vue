<template>
	<div class="share-box">
		<player></player>
		<link-list :links="links" :artist="artist" :title="title"></link-list>
	</div>
</template>

<script>
import LinkList from './LinkList';
import Player from './Player';

export default {
	name: 'ShareBox',
	components: {
		LinkList,
		Player
	},
	data() {
		return {
			artist: 'OPROER',
			title: 'Dolores',
			links: [
				{
					service: 'spotify',
					url:
						'https://open.spotify.com/track/4adwbWyokZ9RTPXXyxAob1'
				},
				{
					service: 'deezer',
					url: 'http://www.deezer.com/track/422073392?app_id=140685'
				},
				{
					service: 'tidal',
					url: 'https://play.google.com/store/music/album?id=Bbzf5sxdmaerqtapd24c74hpfe4&tid=song-T3ayxxyilzfwc2l6rhscu3tl2oa&PCamRefID=LFV_aba0fac4f3935bfa76cc0660c791ae58'
				},
				{
					service: 'apple-music',
					url: 'https://play.google.com/store/music/album?id=Bbzf5sxdmaerqtapd24c74hpfe4&tid=song-T3ayxxyilzfwc2l6rhscu3tl2oa&PCamRefID=LFV_aba0fac4f3935bfa76cc0660c791ae58'
				},
				{
					service: 'itunes',
					url: 'https://play.google.com/store/music/album?id=Bbzf5sxdmaerqtapd24c74hpfe4&tid=song-T3ayxxyilzfwc2l6rhscu3tl2oa&PCamRefID=LFV_aba0fac4f3935bfa76cc0660c791ae58'
				},
				{
					service: 'google-play',
					url: 'https://play.google.com/store/music/album?id=Bbzf5sxdmaerqtapd24c74hpfe4&tid=song-T3ayxxyilzfwc2l6rhscu3tl2oa&PCamRefID=LFV_aba0fac4f3935bfa76cc0660c791ae58'
				},
			]
		};
	}
};
</script>

<style lang="scss">
	.share-box {
		width: 320px;
	}
</style>
