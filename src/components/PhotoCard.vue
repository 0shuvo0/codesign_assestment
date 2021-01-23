<template>
	<div class="gallery-img" :class="{tall: Math.random() > 0.4}">
   	<img :src="photo.src.small" alt="">
   	<div class="overlay">
   		<p class="text-right"><i class="fas fa-heart ibtn"></i><i class="fas fa-plus ibtn"></i></p>
   		<div class="by">
   			<p>{{ photo.photographer }}</p>
   			<a :href="photo.src.large" download><i class="fas fa-download ibtn lg"></i></a>
   		</div>
   	</div>
	</div>
</template>

<style>
.gallery-img{
	position: relative;
}
.gallery-img img{
	width: 100%;
	height: 100%;
}
.gallery-img.tall{
	grid-row: span 2;
}
.gallery-img .overlay{
	padding: 15px;
	color: #fff;
	width: 100%;
	height: 100%;
	background-color: rgba(0, 0, 0, 0.3);
	position: absolute;
	top: 0;
	left: 0;
	display: flex;
	flex-direction: column;
	justify-content: space-between;
	opacity: 0;
	transition: opacity 0.3s;
}
.gallery-img:hover .overlay{
	opacity: 1;
}
.by{
	display: flex;
	justify-content: space-between;
	align-items: center;
}
.ibtn{
	--size: 30px;
	width: var(--size);
	height: var(--size);
	border-radius: 50%;
	text-align: center;
	line-height: var(--size);
	background-color: #fff;
	color: #1B1B1B;
	margin-left: 5px;
}
.ibtn.lg{
	--size: 35px;
	color: #fff;
	background: #00C853;
}
</style>

<script>
export default {
	props: ['photo']
}
</script>