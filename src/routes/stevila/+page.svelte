<script lang="ts">
	let stevilo = 0;
	let sodo: boolean;
	let seznamDeliteljev: number[] = [];
	let vsota = 0;
	function jeSodo(num: number) {
		return num % 2 == 0;
	}
	function izpisiDelitelje(num: number) {
		let delitelji: number[] = [];
		for (let i = 1; i < num; i++) {
			if (num % i == 0) delitelji.push(i);
		}
		return delitelji;
	}
	function vsotaDeljiteljev(nums: number[]) {
		let sestevek = 0;
		for (const i of nums) {
			sestevek += i;
		}
		return sestevek;
	}

	$: {
		sodo = jeSodo(stevilo);
		seznamDeliteljev = izpisiDelitelje(stevilo);
		vsota = vsotaDeljiteljev(seznamDeliteljev);
	}
</script>

<div class="flex flex-col gap-2 items-center justify-center min-h-screen">
	<div>
		<input
			min="0"
			bind:value={stevilo}
			class="border-4 rounded-2xl text-center p-4 text-4xl border-cyan-700"
			type="number"
		/>
	</div>
	<div class=" grid grid-cols-4 gap-4">
		<div class="bg-cyan-700 rounded-xl p-2">
			<p class="text-white text-4xl">število je:</p>
			<p class="text-white text-6xl">{sodo ? 'sodo' : 'liho'}</p>
		</div>
		<div class="bg-cyan-700 rounded-xl p-2">
			<p class="text-white text-4xl">seznam deljiteljev:</p>
			<ul class="flex flex-wrap gap-2">
				{#each seznamDeliteljev as st}
					<li class="bg-white p-2 rounded-xl">{st}</li>
				{/each}
				<li class="bg-white p-2 rounded-xl">{stevilo}</li>
			</ul>
		</div>
		<div class="bg-cyan-700 rounded-xl p-2">
			<p class="text-white text-4xl">vsota deliteljev števila je:</p>
			<p class="text-white text-6xl">{vsota}</p>
		</div>
		<div class="bg-cyan-700 rounded-xl p-2">
			<p class="text-white text-4xl">ali je število popolno:</p>
			<p class="text-white text-6xl">{vsota == stevilo ? '☑️' : '❌'}</p>
		</div>
	</div>
</div>
