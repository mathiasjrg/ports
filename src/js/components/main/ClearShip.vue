<template>
	<div class="flex items-center justify-center mt-2 mb-4 text-white">
		<span>Clear ship : </span>
		
		<div class="ml-4">
			<button class="w-6 h-6 mr-1 text-sm text-white border border-white rounded-full" @click="clearShip(1)">1</button>
			<button class="w-6 h-6 mr-1 text-sm text-white border border-white rounded-full" @click="clearShip(2)">2</button>
			<button class="w-6 h-6 mr-1 text-sm text-white border border-white rounded-full" @click="clearShip(3)">3</button>
			<button class="w-6 h-6 text-sm text-white border border-white rounded-full" @click="clearShip(4)">4</button>
		</div>
	</div>
</template>

<script>
	export default {
		methods: {
			/**
			 * Clear the crew assignments for the specified ship
			 * @param  {int} number 
			 * @return {void}        
			 */
			clearShip(number){
				this.$root.captains.forEach(captain => {
					if(captain.ship == number){captain.ship = 0;}
				});

				this.$root.crew.forEach(crew => {
					if(crew.ship == number){crew.ship = 0;}
				});

				this.$root.save();
			}
		}
	}
</script>