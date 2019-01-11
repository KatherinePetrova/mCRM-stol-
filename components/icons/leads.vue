<template>
	<div class="lead" :class="{w: clicked==1}">
		<svg version="1.1" id="Layer_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" width="29.037px" height="35.9px" viewBox="-0.765 -1 29.037 35.9" enable-background="new -0.765 -1 29.037 35.9" xml:space="preserve">
			<path :class="{sW: clicked==1, fW: clicked==1}" stroke-miterlimit="10" d="M20.818,9.439c3.591,2.312,5.97,6.347,5.97,10.938c0,7.18-5.817,13-13.002,13c-7.183,0-13-5.82-13-13c0-1.455,0.237-2.855,0.68-4.162l0.072-0.422"/>
			<defs>
				<path id="SVGID_l1_" d="M26.786,20.374c0,7.181-5.815,13-13.002,13c-7.181,0-13-5.819-13-13c0-7.181-8.445-23.243,13-23.243C24.846-2.867,26.786,13.195,26.786,20.374z"/>
			</defs>
			<clipPath id="SVGID_l2_">
				<use xlink:href="#SVGID_l1_"  overflow="visible"/>
			</clipPath>
			<g clip-path="url(#SVGID_l2_)">
				<path :class="{sW: clicked==1, fB: clicked==1}" stroke-miterlimit="10" d="M9.289,40.257v-4.631c-3.267-0.146-6.435-1.021-8.285-2.096l1.462-5.701c2.047,1.121,4.923,2.146,8.09,2.146c2.778,0,4.682-1.064,4.682-3.021c0-1.854-1.562-3.021-5.167-4.236c-5.217-1.758-8.773-4.192-8.773-8.921c0-4.289,3.021-7.651,8.236-8.676V0.49h4.776v4.29c3.269,0.146,5.461,0.828,7.065,1.607l-1.413,5.508c-1.271-0.536-3.509-1.657-7.023-1.657c-3.168,0-4.189,1.364-4.189,2.729c0,1.606,1.706,2.632,5.854,4.189c5.806,2.048,8.144,4.729,8.144,9.115c0,4.338-3.067,8.039-8.678,9.014v4.975L9.289,40.257L9.289,40.257z"/>
			</g>
		</svg>
		Сделки
	</div>
</template>

<script>
export default {
	props: ['clicked']
}	
</script>

<style scoped>

	div.lead {
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

	path {
		fill: none;
		stroke: #AFAFAF;
	}

	div.lead:hover svg path {
		stroke: white;
	}

	div.lead:hover {
		background-color: rgba(255, 255, 255, 0.1)
	}

	.sB {stroke: blue;} .sW {stroke: white;}
	.fB {fill: blue;} .fW {fill: white;} 
	.w {color: white; background-color: rgba(255, 255, 255, 0.1)}

</style>