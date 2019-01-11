<template>
	<div class="mail" :class="{w: clicked==4}">
		<svg version="1.1" id="Layer_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" width="32.803px" height="29.025px" viewBox="0 0 32.803 29.025" enable-background="new 0 0 32.803 29.025" xml:space="preserve">
			<path stroke-miterlimit="10" d="M24.754,22.877"/>
			<path :class="{sB: clicked==4, fW: clicked==4}" stroke-miterlimit="10" d="M24.407,5.707c-2.377-2.592-5.786-4.217-9.597-4.217c-7.179,0-13,5.821-13,13c0,7.184,5.82,13,13,13c3.995,0,7.561-1.789,9.947-4.608l1.514-1.854"/>
			<defs>
				<path id="SVGID_m1_" d="M35.832,14.487c0,7.184-13.83,13-21.024,13c-7.178,0-12.998-5.816-12.998-13c0-7.178,5.819-13,12.998-13C22.002,1.488,35.832-1.167,35.832,14.487z"/>
			</defs>
			<clipPath id="SVGID_m2_"><use xlink:href="#SVGID_m1_"  overflow="visible"/></clipPath>
			<g clip-path="url(#SVGID_m2_)">
				<path :class="{sW: clicked==4, fB: clicked==4}" stroke-miterlimit="10" d="M26.567,20.443c-0.554,1.377-2.111,2.494-3.486,2.494H3.126c-1.375,0-2.046-1.117-1.495-2.494L6.284,8.816c0.553-1.375,1.396-3.008,3.37-3.008h19.778c1.979,0,2.334,1.632,1.782,3.008L26.567,20.443z"/>
				<polyline :class="{sW: clicked==4}" stroke-miterlimit="10" points="27.563,9.646 15.753,16.291 9.275,9.646 "/>
				<line :class="{sW: clicked==4}" stroke-miterlimit="10" x1="5.044" y1="20.301" x2="10.312" y2="16.348"/>
				<line :class="{sW: clicked==4}" stroke-miterlimit="10" x1="23.502" y1="20.301" x2="20.867" y2="16.348"/>
			</g>
		</svg>
		Почта
	</div>
</template>

<script>
export default {
	props: ['clicked']
}	
</script>

<style scoped>

	div.mail {
		height: 100%;
		width: 100%;

		display: flex;
		justify-content: center;
		align-items: center;
		flex-direction: column;
	}

	div.mail:hover svg path {
		stroke: white;
	}

	div.mail:hover svg g path, div.mail:hover svg g polyline, div.mail:hover svg g line {
		stroke: white;
	}

	svg {
		height: 50%;
	}

	svg path {
		fill: none;
		stroke: #AFAFAF;
	}
	
	g path {
		fill: none;
		stroke: #AFAFAF;
	}

	polyline {
		fill: none;
		stroke: #AFAFAF;
	}

	line {
		fill: none;
		stroke: #AFAFAF;
	}

	.sW {stroke: white;} .sB {stroke: blue;}
	.fW {fill: white;} .fB {fill: blue;}

	.w {color: white; background-color: rgba(255, 255, 255, 0.1)}

	div.w:hover svg path {
		stroke: blue;
	}

	div.w:hover svg g path, div.w:hover svg g polyline, div.w:hover svg g line {
		stroke: white;
	}

</style>