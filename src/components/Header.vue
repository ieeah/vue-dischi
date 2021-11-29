<template>
	<header>
		<img class="brand_logo" src="@/assets/logo.png" alt="">

		<form action="">
			<select v-model="selectedGenre" @change="$emit('genResearch', selectedGenre)">
				<option value="All">All Genres</option>
				<option value="Rock">Rock</option>
				<option value="Pop">Pop</option>
				<option value="Jazz">Jazz</option>
				<option value="Metal">Metal</option>
				<!-- <option value="All">All genres</option> -->
				<!-- <option v-for="(disco, i) in allGenresListed" :key="`${disco}`" value="`${disco.genre}`">{{allGenresListed[i]}}</option> -->
			</select>
			<button @click.prevent="$emit('genResearch', selectedGenre)">Cerca</button>
		</form>
	</header>
</template>

<script>
export default {
	name: 'Header',
	props: {
		totAlbums: Array,
	},
	created() {
		this.setAvailableGenres();
	},
	data() {
		return {
			selectedGenre: '',
			allGenresListed: [],
		};
	},
	methods: {
		setAvailableGenres() {
			this.totAlbums.forEach(disco => {
				if (!this.allGenresListed.includes(disco.genre)) {
					this.allGenresListed.push(disco.genre);
					console.log();
						// TODO - capire sta cosa perché PORCODDIO le facevo facili e invece da due giorni sono morto ammazzato?
					
				}
			});
		},
	},
}
</script>

<style scoped lang="scss">
@import '@/styles/globals.scss';
@import '@/styles/vars.scss';

header {
	background-color: $secondary-color;
	padding: 10px;
	display: flex;
	align-items: center;
	justify-content: space-between;
}

.brand_logo {
	height: 48px;
}

select,
button {
	padding: 5px 10px;
}

select {
	width: 100px;
	text-align: center;
}

button {
	margin-left: 15px;
}

</style>