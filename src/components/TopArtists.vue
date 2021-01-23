<template>
	<div class="gallery-img tall artists">
		<img class="bg" src="../assets/artist.jpeg" alt="">
		<div class="overlay">
			<p>Featured Artists</p>
			<div class="loader" v-if="loading">
				<span class="circle"></span>
			</div>
			<div class="artist" v-for="(artist, index) in artists" :key="index">
				<img :src="artist.src.small" alt="">
				<div class="info">
					<p>{{ artist.photographer }}</p>
					<p class="fcount">{{ (Math.random() * 5).toFixed(2)  }}M Followers</p>
				</div>
			</div>
		</div>
	</div>
</template>

<style>
.artists{
	position: relative;
}
.artists .bg{
	z-index: -1;
	height: 100%;
	width: 100%;
	position: absolute;
	top: 0;
	left: 0;
}

.artists .overlay{
	padding: 15px;
	color: #fff;
	width: 100%;
	height: 100%;
	background-color: rgba(0, 0, 0, 0.3);
}
.artists .overlay p{
	font-weight: 500;
}

.artist{
	margin: 5px 0;
	display: flex;
	align-items: center;
}
.artist img{
	height: 50px !important;
	width: 50px !important;
	border-radius: 50%;
	border: 2px solid #fff;
	margin-right: 5px;
}
.artist .info .fcount{
	font-weight: 400;
	font-size: 0.8em;
	margin-top: 3px;
}
</style>

<script>
import pexelsClient from '@/utils/pexels.js'
export default {
	data: () => ({
		artists: [],
		loading: true
	}),
	mounted(){
		pexelsClient.photos.search({ query: "person", per_page: 4 }).then(res => {
			this.artists = res.photos
			this.loading = false
		})
	}
}
</script>