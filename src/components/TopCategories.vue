<template>
	<div class="top-categories">
		<p>Top Categories</p>
		<p class="pod">Photo of the day <span>by</span> <u>John Doe</u></p>
		<div class="categories-wrapper">
		<div class="categories">
			<div class="category">
				<img src="../assets/topcats/workspace.jpeg" alt="">
				<div class="overlay">Workspace</div>
			</div>
			<div class="category">
				<img src="../assets/topcats/summer.jpeg" alt="">
				<div class="overlay">Summer</div>
			</div>
			<div class="category">
				<img src="../assets/topcats/food.jpeg" alt="">
				<div class="overlay">Food</div>
			</div>
			<div class="category">
				<img src="../assets/topcats/gravity.jpeg" alt="">
				<div class="overlay">Gravity</div>
			</div>
			<div class="category">
				<img src="../assets/topcats/city.jpeg" alt="">
				<div class="overlay">City</div>
			</div>
			<div class="category">
				<img src="../assets/topcats/flower.jpeg" alt="">
				<div class="overlay">Flower</div>
			</div>
			<div class="category">
				<img src="../assets/topcats/car.jpeg" alt="">
				<div class="overlay">Car</div>
			</div>
		</div>
		</div>
		<i class="fas fa-arrow-right indicator"></i>
	</div>
</template> 

<style>
.top-categories{
	background-color: #fff;
	padding: 10px 20px;
	position: relative;
}
.top-categories .indicator{
	color: #1F1F1F;
	height: 30px;
	width: 30px;
	text-align: center;
	line-height: 30px;
	border-radius: 50%;
	background-color: #fff;
	box-shadow: 0 3px 5px rgba(0, 0, 0, 0.3);
	position: absolute;
	right: 20px;
	bottom: 50%;
	font-size: 0.9em;
	transform: translate(50%, 75%);
}
.top-categories p{
	font-weight: 700;
	color: #0B0B0B;
	margin-bottom: 5px;
}
.categories-wrapper{
	height: 80px;
	overflow: scroll;
}
.categories-wrapper .categories{
	height: 100%;
	width: 970px;
	display: flex;
}
.categories-wrapper .category{
	flex-shrink: 0;
	margin-right: 10px;
	animation: 0.6s slidein linear;
}
@keyframes slidein{
	0%{
		opacity: 0;
		transform: translateX(150px);
	}
	100%{
		opacity: 1;
		transform: translateX(0);
	}
}
.categories-wrapper .category:last-child{
	margin-right: 0;
}
.categories-wrapper .category, .categories-wrapper .category img{
	height: 80px;
	width: 130px;
	position: relative;
}
.categories-wrapper .category .overlay{
	position: absolute;
	top: 0;
	left: 0;
	width: 100%;
	height: 100%;
	background-color: rgba(0, 0,  0, 0.3);
	color: #fff;
	text-align: center;
	line-height: 80px;
}



.pod{
	color: #fff !important;
	position: absolute;
	top: -25px;
	right: 0;
	font-weight: 400;
}
.pod span{
	opacity: 0.8;
}
</style>