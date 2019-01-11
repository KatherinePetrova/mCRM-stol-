<template>
	<div class="task" :class="{w: clicked==2}">
		<svg version="1.1" id="Layer_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" width="30.979px" height="30.406px" viewBox="0 0 30.979 30.406" enable-background="new 0 0 30.979 30.406" xml:space="preserve">
			<path :class="{fW: clicked==2, sR: clicked==2, def: clicked!=2}" stroke-miterlimit="10" d="M14.502,2.914c7.18,0,13,5.821,13,13.001c0,7.185-5.82,13.006-13,13.006c-7.182,0-13.001-5.821-13.001-13.006C1.502,8.735,7.321,2.914,14.502,2.914z"/>
			<polyline :class="{sR: clicked==2, def: clicked!=2, fN: clicked==2}" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" stroke-miterlimit="10" points="28.961,2.017 14.085,21.023 8.956,15.74 "/>
		</svg>
		Задачи
	</div>
</template>

<script>
export default {
	props: ['clicked']
}	
</script>

<style scoped>

	div.task {
		height: 100%;
		width: 100%;

		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
	}

	svg {
		height: 50%;
	}

	path.def {
		fill: none;
		stroke: #AFAFAF;
	}

	polyline.def {
		fill: none;
		stroke: #AFAFAF;
	}

	div.task:hover {
		background-color: rgba(255, 255, 255, 0.1)
	}

	div.task:hover svg path.def, div.task:hover svg polyline.def {
		stroke: white;
	}

	.fW {fill: white;} .fR {fill: red;} .fN {fill: none;}
	.sR {stroke: red;}

	.w {color: white; background-color: rgba(255, 255, 255, 0.1)}

</style>