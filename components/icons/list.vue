<template>
	<div class="list" :class="{w: clicked==3}">
		<svg xmlns="http://www.w3.org/2000/svg" width="55" height="64" viewBox="0 0 55 64">
  			<path :class="{def: clicked!=3, fB: clicked==3}" id="List" d="M198,1435.62V1436h-0.287a27.5,27.5,0,0,1-42.427,0H155v-0.38a27.339,27.339,0,0,1,0-34.18V1386h43v15.38A27.425,27.425,0,0,1,198,1435.62Zm-43-30.77a25.324,25.324,0,0,0,0,27.32v-27.32ZM196,1388H157v46l1,2h-0.014a25.425,25.425,0,0,0,37.03,0H195l1-2v-46Zm2,44.17a25.359,25.359,0,0,0,0-27.34v27.34ZM173,1431h18v2H173v-2Zm0-15h18v2H173v-2Zm0-15h18v2H173v-2Zm0-6h8v2h-8v-2Zm-11,30h8v8h-8v-8Zm2,6h4v-4h-4v4Zm-2-21h8v8h-8v-8Zm2,6h4v-4h-4v4Zm-2-21h8v8h-8v-8Zm2,6h4v-4h-4v4Zm17,11h-8v-2h8v2Zm0,15h-8v-2h8v2Zm-23-45h37v2H158v-2Z" transform="translate(-149 -1382)"/>
		</svg>
		Списки
	</div>
</template>

<script>
export default {
	props: ['clicked']
}		
</script>

<style scoped>

	div.list {
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
		fill-rule: evenodd;
		fill: #AFAFAF;
	}

	div.list:hover svg path.def {
		fill: white;
	}

	div.list:hover {
		background-color: rgba(255, 255, 255, 0.1)
	}

	.fB {fill: blue;} .fW {fill: white;} .fN {fill: none;}
	.sB {stroke: blue;}
	
	.w {color: white; background-color: rgba(255, 255, 255, 0.1)}

</style>