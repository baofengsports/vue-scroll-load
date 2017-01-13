<template>
	<div class="loading-circle">
  		<div class="loading-circle1 loading-circle-ios"></div>
  		<div class="loading-circle2 loading-circle-ios"></div>
  		<div class="loading-circle3 loading-circle-ios"></div>
  		<div class="loading-circle4 loading-circle-ios"></div>
  		<div class="loading-circle5 loading-circle-ios"></div>
  		<div class="loading-circle6 loading-circle-ios"></div>
  		<div class="loading-circle7 loading-circle-ios"></div>
  		<div class="loading-circle8 loading-circle-ios"></div>
  		<div class="loading-circle9 loading-circle-ios"></div>
  		<div class="loading-circle10 loading-circle-ios"></div>
  		<div class="loading-circle11 loading-circle-ios"></div>
  		<div class="loading-circle12 loading-circle-ios"></div>
	</div>
</template>

<script>
export default {
	name : 'loading'
}
</script>

<style lang="scss" scoped>
.loading-circle{
	width: 45px;
	height: 45px;
	position: relative;

	.loading-circle-ios{
		width: 100%;
		height: 100%;
		position: absolute;
		left: 0;
		top: 0;
		z-index: 10;

		&:before{
			content: '';
			display: block;
  			margin: 0 auto;
  			width: 5%;
  			height: 25%;
  			background-color: #fff;
  			-webkit-animation: loading-circleFadeDelay-ios 1.2s infinite ease-in-out both;
          			animation: loading-circleFadeDelay-ios 1.2s infinite ease-in-out both;
		}
	}
	
}
.loading-circle .loading-circle2 {
  -webkit-transform: rotate(30deg);
      -ms-transform: rotate(30deg);
          transform: rotate(30deg);
}
.loading-circle .loading-circle3 {
  -webkit-transform: rotate(60deg);
      -ms-transform: rotate(60deg);
          transform: rotate(60deg);
}
.loading-circle .loading-circle4 {
  -webkit-transform: rotate(90deg);
      -ms-transform: rotate(90deg);
          transform: rotate(90deg);
}
.loading-circle .loading-circle5 {
  -webkit-transform: rotate(120deg);
      -ms-transform: rotate(120deg);
          transform: rotate(120deg);
}
.loading-circle .loading-circle6 {
  -webkit-transform: rotate(150deg);
      -ms-transform: rotate(150deg);
          transform: rotate(150deg);
}
.loading-circle .loading-circle7 {
  -webkit-transform: rotate(180deg);
      -ms-transform: rotate(180deg);
          transform: rotate(180deg);
}
.loading-circle .loading-circle8 {
  -webkit-transform: rotate(210deg);
      -ms-transform: rotate(210deg);
          transform: rotate(210deg);
}
.loading-circle .loading-circle9 {
  -webkit-transform: rotate(240deg);
      -ms-transform: rotate(240deg);
          transform: rotate(240deg);
}
.loading-circle .loading-circle10 {
  -webkit-transform: rotate(270deg);
      -ms-transform: rotate(270deg);
          transform: rotate(270deg);
}
.loading-circle .loading-circle11 {
  -webkit-transform: rotate(300deg);
      -ms-transform: rotate(300deg);
          transform: rotate(300deg); 
}
.loading-circle .loading-circle12 {
  -webkit-transform: rotate(330deg);
      -ms-transform: rotate(330deg);
          transform: rotate(330deg); 
}
.loading-circle .loading-circle2:before {
  -webkit-animation-delay: -1.1s;
          animation-delay: -1.1s; 
}
.loading-circle .loading-circle3:before {
  -webkit-animation-delay: -1s;
          animation-delay: -1s; 
}
.loading-circle .loading-circle4:before {
  -webkit-animation-delay: -0.9s;
          animation-delay: -0.9s; 
}
.loading-circle .loading-circle5:before {
  -webkit-animation-delay: -0.8s;
          animation-delay: -0.8s; 
}
.loading-circle .loading-circle6:before {
  -webkit-animation-delay: -0.7s;
          animation-delay: -0.7s; 
}
.loading-circle .loading-circle7:before {
  -webkit-animation-delay: -0.6s;
          animation-delay: -0.6s; 
}
.loading-circle .loading-circle8:before {
  -webkit-animation-delay: -0.5s;
          animation-delay: -0.5s; 
}
.loading-circle .loading-circle9:before {
  -webkit-animation-delay: -0.4s;
          animation-delay: -0.4s;
}
.loading-circle .loading-circle10:before {
  -webkit-animation-delay: -0.3s;
          animation-delay: -0.3s;
}
.loading-circle .loading-circle11:before {
  -webkit-animation-delay: -0.2s;
          animation-delay: -0.2s;
}
.loading-circle .loading-circle12:before {
  -webkit-animation-delay: -0.1s;
          animation-delay: -0.1s;
}
@-webkit-keyframes loading-circleFadeDelay {
  0%, 39%, 100% { opacity: 0; }
  40% { opacity: 1; }
}
@keyframes loading-circleFadeDelay {
  0%, 39%, 100% { opacity: 0; }
  40% { opacity: 1; } 
}
@-webkit-keyframes loading-circleFadeDelay-ios {
  0%, 39%, 100% { opacity: .3; }
  40% { opacity: 1; }
}
@keyframes loading-circleFadeDelay-ios {
  0%, 39%, 100% { opacity: .3; }
  40% { opacity: 1; } 
}
</style>
