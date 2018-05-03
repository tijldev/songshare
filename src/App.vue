<template>
  <div id="app">
    <ShareBox />
    <p class="copyright">&copy; OPROER</p>
  </div>
</template>

<script>
import ShareBox from './components/ShareBox';

export default {
	name: 'App',
	components: {
		ShareBox
	}
};
</script>

<style>
body {
	margin: 0;
}

#app {
	font-family: 'Avenir', Helvetica, Arial, sans-serif;
	text-align: center;
	color: #2c3e50;

	min-height: 100vh;

	display: flex;
	align-items: center;

	flex-direction: column;
	position: relative;

	overflow: hidden;
}

#app::before {
	content: '';
	position: absolute;
	width: 100%;
	height: 100%;
		background-image: linear-gradient(
			to right,
			rgba(0, 0, 0, 0.9) 0%,
			rgba(0, 0, 0, 0.9) 100%
		),
		url('/dolores/static/cover.jpg');
	background-size: cover;
  background-position: center;
	filter: blur(15px);
  z-index: -5;
	transform: scale(1.2);
}

.copyright {
	font-family: 'Gill Sans', 'Gill Sans MT', Calibri, 'Trebuchet MS',
		sans-serif;
	color: white;
  background-color: darkslategrey;
  width:320px;
  margin: 0;
  padding: 10px 0;
}
</style>
