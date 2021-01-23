<template>
	<div class="banner">
		<img src="../assets/sfg.jpeg" alt="">
		<div class="overlay"></div>
		<div class="content">
			<h1>Your local source of high quality images
and videos directly from their creators</h1>
			<div class="search-bar">
				<input type="text" placeholder="Search Photos and Videos" @change="handleInputChange" v-model="search">
				<i class="fas fa-search" @click="handleInputChange"></i>
			</div>
			<p><span>Recommended:</span> summer, food, covid-19, real estate, love</p>
		</div>
		<TopCategories />
	</div>
</template>

<style>
.banner{
	height: calc(100vh - 200px);
	position: relative;
	margin-bottom: 80px;
}
.banner img, .banner .overlay{
	position: absolute;
	height: 100%;
	width: 100%;
}
.banner .overlay{
	background-color: rgba(0, 0, 0, 0.4);
}
.banner .content{
	color: #fff;
	position: absolute;
	top: 50%;
	left: 50%;
	width: 80%;
	transform: translate(-50%, -50%);
}
.content h1{
	font-size: 1.5em;
}
.content p{
	font-weight: 0.9em;
	color: rgba(255, 255, 255, 0.8);
}
.content p span{
	color: rgba(255, 255, 255, 1);
}

.search-bar{
	height: 45px;
	margin: 10px 0;
	background-color: #fff;
	border-radius: 30px;
	overflow: hidden;
	display: flex;
	align-items: center;
}
.search-bar input{
	height: 100%;
	border: none;
	outline: none;
	flex-grow: 1;
	padding: 0 1em 0 1.5em;
}
.search-bar i{
	margin-right: 1.5em;
	color: #161616;
}

.banner .top-categories{
	position: absolute;
	bottom: 0;
	left: 5%;
	width: 90%;
	transform: translateY(50%);
}
</style>

<script>
import TopCategories from '@/components/TopCategories.vue'
export default {
	components: {
		TopCategories
	},
	data: () => ({
		search: ""
	}),
	methods: {
		handleInputChange(){
			this.$emit('search', this.search)
		}
	}
}
</script>