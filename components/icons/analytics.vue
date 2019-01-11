<template>
	<div class="analytics" :class="{w: clicked==5}">
		<svg version="1.1" id="Layer_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" width="38.945px" height="29px" viewBox="0 0 38.945 29" enable-background="new 0 0 38.945 29" xml:space="preserve">
			<path :class="{a1: clicked!=5, fW: clicked==5, sR: clicked==5}" stroke-miterlimit="10" d="M19.622,1.758c7.177,0,12.995,5.82,12.995,13c0,7.182-5.816,13-12.995,13c-7.18,0-13-5.818-13-13C6.622,7.578,12.442,1.758,19.622,1.758z"/><path :class="{a2: clicked!=5, fR: clicked==5}" d="M3.766,24.279c1.54,0,2.791-1.254,2.791-2.793c0-0.445-0.114-0.857-0.302-1.234l6.396-5.542c0.448,0.312,0.996,0.499,1.582,0.499c0.922,0,1.733-0.456,2.242-1.146l5.473,2.188c-0.017,0.114-0.033,0.229-0.033,0.353c0,1.541,1.258,2.796,2.788,2.796c1.539,0,2.791-1.255,2.791-2.796c0-0.604-0.194-1.163-0.524-1.624l7.021-8.427c0.361,0.173,0.768,0.277,1.188,0.277c1.541,0,2.793-1.256,2.793-2.795c0-1.538-1.252-2.792-2.793-2.792c-1.54,0-2.791,1.254-2.791,2.792c0,0.604,0.199,1.168,0.524,1.622l-7.021,8.431c-0.359-0.174-0.764-0.277-1.188-0.277c-0.92,0-1.728,0.457-2.233,1.146l-5.476-2.193c0.02-0.112,0.035-0.229,0.035-0.354c0-1.536-1.254-2.791-2.793-2.791c-1.54,0-2.792,1.255-2.792,2.791c0,0.45,0.113,0.86,0.3,1.237l-6.396,5.546c-0.451-0.312-0.995-0.498-1.582-0.498c-1.542,0-2.793,1.254-2.793,2.795C0.973,23.025,2.224,24.279,3.766,24.279z"/>
		</svg>
		Аналитика
	</div>
</template>

<script>
export default {
	props: ['clicked']
}	
</script>

<style scoped>

	div.analytics {
		height: 100%;
		width: 100%;

		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
	}

	div.analytics:hover svg path.a1 {
		stroke: white;
	}

	div.analytics:hover svg path.a2 {
		fill: white;
	}

	svg {
		height: 50%;
	}

	svg path.a1 {
		fill: none;
		stroke: #AFAFAF;
	}
	
	svg path.a2 {
		fill: #AFAFAF;
	}

	.sR {stroke: red;}
	.fR {fill: red;} .fW {fill: white;}

	.w {color: white; background-color: rgba(255, 255, 255, 0.1)}

</style>