<script>

</script>

<main
	class="bg-purple-800 h-full w-full rounded-sm flex items-center justify-center"
>
	<div class="flex-col p-10 bg-gray-100 rounded">
		<div class="flex flex-col">
			<textarea class="resize-none text-sm rounded-md mb-1 h-20">1000 + 200 + 100 - 46 = 1254</textarea>
			<p class="text-gray-800 font-bold m-2 p-1 text-2xl text-right">1254</p>
		</div>

		
		<div class="inline-grid grid-cols-2 grid-rows-1 h-full w-full">
			<button class='text-sm text-gray-500 m-4'>
				clear all
			</button>
			<button class="flex items-center justify-end border-none pr-1">
				<svg class="h-8 w-8 text-gray-500 hover:text-red-500"  width="24" height="24" viewBox="0 0 24 24" stroke-width="1" stroke="currentColor" fill="none" stroke-linecap="round" stroke-linejoin="round">  <path stroke="none" d="M0 0h24v24H0z"/>  <path d="M20 6a1 1 0 0 1 1 1v10a1 1 0 0 1 -1 1h-11l-5 -5a1.5 1.5 0 0 1 0 -2l5 -5Z" />  <path d="M12 10l4 4m0 -4l-4 4" /></svg>
			</button>
		</div>
		
		<div class="flex flex-1 flex-row">
			<div class="flex-initial w-64 p-1">
				<div class="inline-grid grid-cols-3 grid-rows-4 gap-4 h-full w-full">
					<button class="bg-gray-100 hover:bg-gray-200 text-gray-800 font-bold rounded">7</button>
					<button class="bg-gray-100 hover:bg-gray-200 text-gray-800 font-bold rounded">8</button>
					<button class="bg-gray-100 hover:bg-gray-200 text-gray-800 font-bold rounded">9</button>
					<button class="bg-gray-100 hover:bg-gray-200 text-gray-800 font-bold rounded">6</button>
					<button class="bg-gray-100 hover:bg-gray-200 text-gray-800 font-bold rounded">5</button>
					<button class="bg-gray-100 hover:bg-gray-200 text-gray-800 font-bold rounded">4</button>
					<button class="bg-gray-100 hover:bg-gray-200 text-gray-800 font-bold rounded">3</button>
					<button class="bg-gray-100 hover:bg-gray-200 text-gray-800 font-bold rounded">2</button>
					<button class="bg-gray-100 hover:bg-gray-200 text-gray-800 font-bold rounded">1</button>
					<button class="bg-gray-100 hover:bg-gray-200 text-gray-800 font-bold rounded">,</button>
					<button class="bg-gray-100 hover:bg-gray-200 text-gray-800 font-bold rounded">0</button>
					<button class="bg-yellow-600 hover:bg-yellow-700 text-white font-bold py-2 px-4 rounded-full">=</button>
				</div>
			</div>

			<div class="flex-initial w-16 p-1">
				<div class="grid grid-cols-1 grid-rows-4 gap-4">
					<button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">+</button>
					<button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">-</button>
					<button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">*</button>
					<button class="bg-blue-500 hover:bg-blue-700 text-white font-bold py-2 px-4 rounded">/</button>
				</div>
			</div>
		</div>
	</div>
</main>
