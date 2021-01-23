<template>
	<span class="popupmenu">
		...
		<div class="menu">
			<a href="#" v-for="(link, index) in links" :key="index">{{ link }}</a>
			<div class="links">
				<i class="fab fa-facebook-f"></i>
				<i class="fab fa-github"></i>
				<i class="fab fa-instagram"></i>
				<i class="fab fa-linkedin"></i>
				<i class="fab fa-google"></i>
				
			</div>
		</div>
	</span>
</template>

<style>
.popupmenu{
	position: relative;
}
.popupmenu .menu{
	position: absolute;
	z-index: 9;
	left: -15px;
	top: calc(100% + 15px);
	background-color: #171717;
	min-width: 220px;
	display: none;
}
.popupmenu:hover .menu{
	display: block;
}
.popupmenu .menu:before{
	content: '';
	display: block;
	position: absolute;
	top: -8px;
	left: 14px;
	width: 16px;
	height: 16px;
	background-color: #171717;
	transform: rotate(45deg);
	z-index: -1;
}
.popupmenu .menu a{
	margin: 0 !important;
	display: block;
	padding: 5px 15px;
	color: rgba(255, 255, 255, 0.8);
	font-weight: 400;
}
.popupmenu .menu a:hover{
	color: rgba(255, 255, 255, 1);
	background-color: rgba(255, 255, 255, 0.1);
}
.popupmenu .menu .links{
	padding: 8px 15px;
	display: flex;
	justify-content: space-between;
}
.popupmenu .menu .links i{
	height: 30px;
	width: 30px;
	text-align: center;
	line-height: 30px;
	color: #171717;
	border-radius: 50%;
	background-color: var(--primary-color);
}
</style>

<script>
export default {
	data: () => ({
		links: ['About Click Motto', 'Pricing', 'License', 'Partnerships', 'Blog', 'Help', 'Join The Team']
	})
}
</script>