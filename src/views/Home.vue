<template>
  <div class="home">
    <Banner @search="searchText" />
    <div class="main">
    	<div class="nav">
    		<div class="cats">
    			<a href="#" class="active" @click="searchText('')">All</a>
    			<a href="#" @click="searchText('photos')">Photos</a>
    			<a href="#" @click="searchText('videos')">Videos</a>
    			<a href="#" @click="searchText('')">Freebies</a>
    			<a href="#" @click="searchText('')">360</a>
    		</div>
    		<select>
    			<option selected>Recommended</option>
    			<option>Most Recent</option>
    			<option>Most viewed</option>
    			<option>Most Downloaded</option>
    			<option>Most Appreciated</option>
    		</select>
    	</div><!-- /Nav -->
   	
   	<div v-infinite-scroll="next" infinite-scroll-disabled="loading" infinite-scroll-distance="100">
   		<div class="gallery" v-if="photos.length > 0">
   			<TopArtists />
   			<PhotoCard v-for="(photo, index) in photos" :key="index" :photo="photo" />
   		</div>
   	</div>
   
   	<div class="loader" v-if="loading">
   		<span class="circle"></span>
	  </div>
    </div>
  </div>
</template>

<style>
.main{
	background: ;
	margin: 0 5%;
	padding: 0 20px;
}

.main .nav{
	display: flex;
	flex-wrap: wrap;
	justify-content: space-between;
	align-items: center;
}
.main .nav .cats a{
	color: #535353;
	text-decoration: none;
	margin-right: 5px;
	font-weight: 500;
	transition: color 0.1s;
}
.main .nav .cats a.active, .main .nav .cats a:hover{
	color: #000;
}

select{
	border: none;
	outline: none;
	background: none;
}

.gallery{
	display: grid;
	grid-gap: 5px;
	grid-template-columns: repeat(auto-fit, minmax(180px, 1fr));
	grid-auto-rows: 140px;
	margin: 10px 0;
}
</style>

<script>
import Banner from '@/components/Banner.vue'
import TopArtists from '@/components/TopArtists.vue'
import PhotoCard from '@/components/PhotoCard.vue'

import pexelsClient from '@/utils/pexels.js'

export default {
	components: {
		Banner,
		TopArtists,
		PhotoCard
	},
	data: () => ({
		loading: false,
		page: 1,
		photos: [],
		type: "photos",
		query: ""
	}),
	mounted(){
		this.getPhotos()
	},
	methods: {
		getPhotos(){
			this.loading = true
			let p
			if(!this.query.trim()){
				p = pexelsClient[this.type].curated({ page: this.page, per_page: 15 })
			}else{
				p = pexelsClient[this.type].search({ page: this.page, per_page: 15, query: this.query })
			}
			p.then(res => {
				this.loading = false
				let newData = res.photos
				this.photos = [...this.photos, ...newData]
			})
		},
		next(){
			this.page++
			this.getPhotos()
		},
		reset(){
			this.page = 1
			this.photos = []
		},
		searchText(text){
			this.query = text
			this.reset()
			getPhotos()
		}
	}
}
</script>
