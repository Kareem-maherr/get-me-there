<template>
  <div id="Directions">
	<div class="grid grid-cols-12 mt-4 shadow-md">
		<div class="col-span-2 mx-auto">

			<div>
				<ArrowIcon :size="35" />
			</div>

			<div class="h-16 mt-4 w-full">
				<div :class="[isPickupActive ? 'circle-black' : 'circle-grey']"></div>
				<div class="line"></div>
				<div :class="[!isPickupActive ? 'square-black' : 'square-grey']"></div>
			</div>
		</div>
		<div class="col-span-10 pr-4">
			<div class="w-full h-5">
			</div>
			<div class="mb-2 mt-5">
				<AutoCompleteInput 
					Id="firstInput"
					v-model:input="pickup"
					placeholder="Enter Pickup Location"
					@isActive="isPickupActive= true"
				/> 
			</div>
			
			<div class="mb-3">
				<AutoCompleteInput
					Id="secondInput"
					v-model:input="destination"
					placeholder="Where to?"
					@isActive="isPickupActive = false" />
			</div>

		</div>
	</div>

	<div class="flex items-center border-buttom">
		<div class="bg-gray-400 mx-5 my-3.5 p-1.5 rounded-full">
			<MapMarkerIcon :size="30" fillColor="#f5f5f5" />
		</div>
		<div>
			<div class="text-lg text-gray-600">6th of October City</div>
			<div class="text-lg text-gray-400">Cairo, Egypt</div>
		</div>
	</div>
	<div class="flex items-center border-buttom">
		<div class="bg-gray-400 mx-5 my-3.5 p-1.5 rounded-full">
			<MapMarkerIcon :size="30" fillColor="#f5f5f5" />
		</div>
		<div>
			<div class="text-lg text-gray-600">Bisköpsgården</div>
			<div class="text-lg text-gray-400">Göteborg, Svergie</div>
		</div>
	</div>
	
  </div>
</template>

<script setup>
	import AutoCompleteInput from '../components/AutoCompleteInput.vue'

	import { ref } from 'vue'

	import ArrowIcon from 'vue-material-design-icons/ArrowLeft.vue'
	import MapMarkerIcon from 'vue-material-design-icons/MapMarker.vue'

	var isPickupActive = ref(true)
	var pickup = ref('')
	var destination = ref('')

</script>

<style lang="scss" scoped>
	#Directions {

		.background-color{
			background-color: rgb(237, 237, 237);
		}

		.background-height{
			height: 100px;
		}

		.circle-black {
			margin: 0 auto;
			width: 9px;
			height: 9px;
			background-color: black;
			border-radius: 100%;
		}

		.circle-grey {
			margin: 0 auto;
			width: 9px;
			height: 9px;
			background-color: rgb(191, 191, 191);
			border-radius: 100%;
		}

		.square-black {
			margin: 0 auto;
			width: 9px;
			height: 9px;
			background-color: black;
		}

		.square-grey {
			margin: 0 auto;
			width: 9px;
			height: 9px;
			background-color: rgb(191, 191, 191);
		}

		.line {
			margin: 0 auto;
			width: 2px;
			height: 45px;
			background-color: rgb(191, 191, 191);
		}
	}


</style>