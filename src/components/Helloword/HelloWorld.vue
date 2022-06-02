<template>
	<!-- INFINITE SCROLL -->
	<div class="container">
		<h1>Hello World, bitches!</h1>
		<div class="container-card-pokemon">
			<div v-for="count in responseApi" :key="this.count++" class="card-pokemon">
				<img :src="count.sprites.front_default" alt="Pokemon"/>
				<br>
				<div class="div-span-name-id">
					<span class="-name">{{ count.name }} </span>
					<span> #{{ count.id }}</span>
				</div>
			</div>
		</div>
	</div>
	
</template>

<script>

import axios from 'axios';

export default {
	name: 'HelloWorld',

	data() {
		return {
			responseApi: [],
			name: '',
			image: '',
			id: 0,
			count: 1
		}
	},

	methods: {
		getApi() {
			for(let i = 1; i <= 25; i++) {
				const urlAPI = `https://pokeapi.co/api/v2/pokemon/${i}`;
				axios
					.get( urlAPI )
					.then( ( response ) => {
						console.log(response.data);
						this.responseApi.push(response.data);
						console.log("responseeeeeee", this.responseApi);
					})
					.catch( ( error ) => {
						console.log( error );
					});
			}
			
		},
	},

	mounted() {
		this.getApi();
	}
}
</script>

<style lang="scss" src="./HelloWorld.scss" />