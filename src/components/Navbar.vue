<template>
<div>
	<div class="navbar container">
		<a href="#" class="brand">
			<svg version="1.1" id="Capa_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px"
			width="100px" height="100px" viewBox="0 0 100 100" enable-background="new 0 0 720 1280" xml:space="preserve">
			<defs></defs><path layer="1" fill="#FFFFFF" fill-opacity="0.0" stroke="#fff" stroke-width="2" stroke-opacity="1.0" stroke-miterlimit="10" d="M3.8146973E-6,2.861023E-6C3.8146973E-6,2.861023E-6,99.99997,2.861023E-6,99.99997,2.861023E-6C99.99997,2.861023E-6,99.99997,99.99998,99.99997,99.99998C99.99997,99.99998,3.8146973E-6,99.99998,3.8146973E-6,99.99998C3.8146973E-6,99.99998,3.8146973E-6,2.861023E-6,3.8146973E-6,2.861023E-6"/>
			<path layer="1" fill="#FFFFFF" fill-opacity="0.0" stroke="#CE7519" stroke-width="20" stroke-opacity="1.0" stroke-miterlimit="10" d="M99.99999,32.787724C99.38772,1.3237953,99.99999,1.3237953,99.99999,1.3237953C99.99999,1.3237953,3.8146973E-6,2.8610223E-6,3.8146973E-6,2.8610223E-6C3.8146973E-6,2.8610223E-6,3.8146973E-6,2.8610223E-6,3.8146973E-6,2.8610223E-6C3.8146973E-6,2.8610223E-6,3.8146973E-6,99.99999,3.8146973E-6,99.99999C3.8146973E-6,99.99999,3.8146973E-6,99.99999,3.8146973E-6,99.99999C3.8146973E-6,99.99999,99.99999,100.000015,99.99999,100.000015C99.99999,100.000015,99.99999,100.000015,99.99999,100.000015C99.99999,100.000015,99.99999,61.0736,99.99999,61.0736"/>
			<path layer="1" fill="#FFFFFF" fill-opacity="0.0" stroke="#CE7519" stroke-width="10" stroke-opacity="1.0" stroke-miterlimit="10" d="M1.2860947,60.43551C21.125786,26.227776,21.125786,26.227776,21.125786,26.227776C21.125786,26.227776,33.87658,71.52819,33.87658,71.52819C33.87658,71.52819,33.87658,71.52819,33.87658,71.52819C33.87658,71.52819,33.87658,71.5282,33.87658,71.5282C33.87658,71.5282,33.87658,71.5282,33.87658,71.5282C33.87658,71.5282,33.87658,71.5282,33.87658,71.5282C33.87658,71.5282,58.282433,41.865356,58.282433,41.865356C58.282433,41.865356,68.253334,74.77597,68.253334,74.77597C68.253334,74.77597,68.253334,74.77597,68.253334,74.77597C68.253334,74.77597,91.462296,51.177673,91.462296,51.177673"/>
			</svg>
			<span>CLICK MOTTO</span>
		</a>
		<nav class="nav">
			<a href="#" class="active">Explore</a>
			<a href="#">Discover</a>
			<a href="#">For Professionals</a>
			<PopupMenu />
			<a href="#" class="btn outline">Submit Photos</a>
			<span class="auth">
				<a href="#">Login</a>
				<a href="#" class="btn">Join Free</a>
			</span>
		</nav>
		<div class="toggle-btn" :class="{active: showSideBar }" @click="showSideBar = !showSideBar">
			<div class="bar a"></div>
			<div class="bar b"></div>
			<div class="bar c"></div>
		</div>
	</div>
	<div class="side-menu-wrapper" :class="{active: showSideBar}" @click="showSideBar = false">
		<div class="side-menu">
			<a href="#" class="menu-item active">Explore</a>
			<a href="#" class="menu-item">Discover</a>
			<a href="#" class="menu-item">For Professional</a>
			<a href="#" class="menu-item"><PopupMenu /></a>
			<a href="#" class="menu-item">Submit Photos</a>
			<a href="#" class="menu-item auth">
				<a href="#">Login</a>
				<a href="#" class="btn">Join Free</a>
			</a>
		</div>
	</div>
</div>
</template>

<style>
.navbar{
	display: flex;
	align-items: center;
	justify-content: space-between;
	padding-top: 8px;
	padding-bottom: 8px;
}
.navbar .brand{
	color: var(--primary-color);
	text-decoration: none;
	font-weight: 700;
	font-size: 1.2em;
	display: flex;
	align-items: center;
}
.navbar .brand svg{
	margin-right: 10px;
	height: 30px;
	width: 30px;
}
.navbar nav a, .navbar nav span{
	margin: 0 0.5em;
	text-decoration: none;
	color: #636363;
	font-weight: 500;
	display: inline-block;
	transition: color 0.1s;
}
.navbar nav a.active, .navbar nav a:hover{
	color: #000;
}

.navbar nav span a.btn{
	color: #fff;
}

navbar nav .auth{
	border-left: 1px solid #636363;
	margin-right: 0;
}
.navbar nav .auth .btn{
	margin-right: 0;
}



.navbar .toggle-btn {
  display: none;
  height: 22px;
  width: 28px;
  position: relative;
}
.navbar .toggle-btn .bar {
  position: absolute;
  left: 0;
  height: 4px;
  width: 100%;
  background-color: var(--text, #0A0A0A);
  border-radius: 5px;
  transition: transform var(--animation-speed, 0.3s), top var(--animation-speed, 0.3s);
}
.navbar .toggle-btn .bar.a {
  transform: translate(5%, 0) scaleX(0.9) rotateZ(0);
}
.navbar .toggle-btn .bar.b {
  top: 50%;
  transform: translate(10%, -50%) scaleX(0.8);
}
.navbar .toggle-btn .bar.c {
  top: 100%;
  transform: translateY(-100%) rotateZ(0);
}
.navbar .toggle-btn.active .bar {
  top: 50%;
  transform-origin: center;
}
.navbar .toggle-btn.active .bar.a {
  transform: translate(0, -50%) scaleX(1) rotateZ(45deg);
}
.navbar .toggle-btn.active .bar.b {
  transform: translate(0, -50%) scaleX(0);
}
.navbar .toggle-btn.active .bar.c {
  transform: translateY(-50%) rotateZ(-45deg);
}



.side-menu-wrapper {
  width: 100vw;
  height: 100vh;
  background-color: transparent;
  position: fixed;
  top: 0;
  left: -100%;
  z-index: 99;
  transition: left var(--animation-speed, 0.3s);
}
.side-menu-wrapper .side-menu {
  width: 240px;
  height: 100%;
  background-color: var(--background, #fff);
  box-shadow: 0 2px 5px var(--shadow-dark, rgba(0, 0, 0, 0.1)), 0 1px 2px var(--shadow-dark, rgba(0, 0, 0, 0.1));
}
.side-menu-wrapper .side-menu .menu-item {
  border-left: 5px solid transparent;
  display: block;
  height: 45px;
  line-height: 45px;
  color: #0A0A0A;
  padding: 0 20px;
  text-decoration: none;
  background-color: rgba(0, 0, 0, 0);
}
.side-menu-wrapper .side-menu .menu-item.active {
  border-left: 5px solid var(--primary-color);
}
.side-menu-wrapper .side-menu .menu-item:hover {
  background-color: rgba(0, 0, 0, 0.01);
  border-left: 5px solid var(--primary-color);
}
.side-menu-wrapper .side-menu .menu-item i {
  width: 25px;
}
.side-menu-wrapper.active {
  left: 0;
}

.side-menu-wrapper .side-menu .menu-item.auth a{
	color: #0a0a0a;
}
.side-menu-wrapper .side-menu .menu-item.auth .btn{
	padding: 0 5px;
	margin-left: 10px;
	color: #fff;
}
</style>

<script>
import PopupMenu from '@/components/PopupMenu.vue'

export default {
	components: {
		PopupMenu
	},
	data: () => ({
		showSideBar: false
	})
}
</script>