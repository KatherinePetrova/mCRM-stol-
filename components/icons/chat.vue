<template>
	<div class="chat">
		<svg version="1.1" id="Layer_1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink" x="0px" y="0px" viewBox="0 0 32 33" xml:space="preserve">
			<path d="M27.3,9.1C24.9,5.4,20.7,3,16,3C8.6,3,2.5,9,2.5,16.5C2.5,23.9,8.6,30,16,30c2.1,0,4.1-0.5,5.9-1.4c1.8,0.9,3.4,1.3,3.4,1.3s-1.5-3.5,2-5.7c2.7-1.4,4.6-4.2,4.6-7.5C31.9,13.3,30,10.4,27.3,9.1z M16,4c3.8,0,7.3,1.7,9.6,4.5c-0.7-0.2-1.4-0.3-2.1-0.3H6.7C9,5.6,12.3,4,16,4z M16,29c-3.6,0-6.8-1.5-9.1-3.9h11.3c0.5,1.3,1.5,2.2,2.5,2.9C19.3,28.6,17.7,29,16,29z M26.9,23.2L26.9,23.2L26.9,23.2c-2.4,1.6-2.9,3.6-2.9,5.2c-1.6-0.6-4-1.7-4.8-3.7L19,24h-0.7H6.1c-1.6-2.1-2.6-4.7-2.6-7.6c0-2.7,0.9-5.2,2.4-7.3h17.6c4.1,0,7.4,3.3,7.4,7.4C30.9,19.4,29.4,21.9,26.9,23.2z"/>
				<g>
					<circle cx="10.1" cy="16.6" r="1.2"/>
					<circle cx="16.1" cy="16.6" r="1.2"/>
					<circle cx="22.1" cy="16.6" r="1.2"/>
				</g>
		</svg>
	</div>
</template>

<script>

</script>

<style scoped>

	div.chat {
		height: 100%;
		width: 100%;

		display: flex;
		justify-content: center;
		align-items: center;
	}

	div.chat:hover svg path, div.chat:hover svg g {
		fill: white;
	}

	svg {
		enable-background:new 0 0 32 33;
		height: 50%;
	}

	svg path, svg g {
		fill: #AFAFAF;
	}

</style>