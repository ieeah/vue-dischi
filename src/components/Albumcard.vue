<template>

<div class="wrapper">
	<div class="album_card">
		<div class="card_img">
			<img :src="poster" :alt="title">
		</div>
		<div class="card_details">
			<h3>{{title}}</h3>
			<h4>{{subTitle}}</h4>
			<h5>{{year}}</h5>
			<h5 class="genre">{{genre}}</h5>
		</div>
	</div>
</div>
	
</template>

<script>

export default {
	name: 'Albumcard',
	props: {
		poster: String,
		title: String,
		subTitle: String,
		year: String,
		genre: String,
	},
}
</script>

<style scoped lang="scss">
@import '@/styles/globals.scss';
@import '@/styles/vars.scss';

.wrapper {
	padding: 10px;
	margin-bottom: 20px;
	width: calc(100% / 8);
}
.album_card {
	text-align: center;
	background-color: $secondary-color;
	padding: 10px;
	height: 100%;
	.card_img {
		margin-bottom: 20px;
		img {
		width: 100%;
	}
	}
	.card_details {
		h3 {
			color: $clear-text;
			padding-bottom: 20px;
			font-size: 1.3rem;
		}
		h4,
		h5 {
			color: $third-color;
			padding-bottom: 8px;
			font-size: 1.1rem;
		}
		.genre {
			color: $clear-text;
			font-size: 1rem;
		}
	}
}

</style>