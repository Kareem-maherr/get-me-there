<template>
	<div>
		<div id="BackButton" class="absolute z-50 rounded-full bg-white p-1 top-8 left-4" @click="goBack()">
			<ArrowLeftIcon :size="40"/>
		</div>
		
		<div id="MapView">
			<div id="VehicleType" class="w-full">
				<div class="w-full h-2 border-t"></div>
				<div class="w-full text-center border-t-2 p-1.5 text-gray-700 text-lg font-semibold">
					Distance - 100
				</div>
				<div class="scrollSection">
					<div class="background-color">
						<div class="flex items-center px-4 py-5">
							<img width="75" src="img/uber/ride.png" />
							<div class="w-full ml-3">
								<div class="flex items-center justify-between">
									<div class="text-2xl mb-1">GMT Comfort</div>
									<div class="text-xl">$500</div>
								</div>
								<div class="text-gray-500">2 Hours</div>
							</div>
						</div>
					</div>
				</div>
			</div>
		</div>
	</div>
</template>

<script setup>
	import ArrowLeftIcon from 'vue-material-design-icons/ArrowLeft.vue'
	import { onMounted } from 'vue'

	onMounted(async () => {
		setTimeout(() => {
			initializeMap()
		}, 50)
	})

	const initializeMap = () => {
		const map = new window.google.maps.Map(document.getElementById("map"), {
        zoom: 4,
        minZoom: 3,
        maxZoom: 17,
        fullscreenControl: false,
        zoomControl: false,
        streetViewControl: false,
        mapTypeControl: false,
		});

		console.log(map)
	}
</script>

<style lang="scss" scoped>
	#MapView {
		width:100%;
		height: 45vh;
		top: 0px;
		left: 0px;
		.background-color{
			background-color: rgb(237, 237, 237);
		}
	}


</style>