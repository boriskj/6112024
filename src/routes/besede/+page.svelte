<script lang="ts">
	let besedilo = '';
	let dolzina = 0;
	let maxDolzina = 999;

	function urediBesedilo(f: string) {
		switch (f) {
			case 'velike':
				besedilo = besedilo.toUpperCase();
				break;
			case 'male':
				besedilo = besedilo.toLowerCase();
				break;
		}
	}

	function nakljucnaBarva() {
		let barva = ['cyan', 'cyan', 'blue', 'blue'];
		let moc = [500, 600, 700, 800, 900];

		return (
			'text-' +
			barva[Math.floor(Math.random() * barva.length)] +
			'-' +
			moc[Math.floor(Math.random() * moc.length)]
		);
	}
</script>

$: {(dolzina = besedilo.length)}

<div class="flex flex-col items-center justify-center min-h-screen">
	<h3 class="text-cyan-700 text text-4xl">besedilko</h3>
	<textarea
		maxlength={maxDolzina}
		bind:value={besedilo}
		class="w-1/2 border-4 border-bg-cyan-700 rounded-lg"
	></textarea>

	<div class="grid grid-cols-3 gap-4">
		<button
			on:click={() => urediBesedilo('velike')}
			class="bg-cyan-700 text-blue-100 rounded-full p-4">velike crke</button
		>

		<button
			on:click={() => urediBesedilo('male')}
			class="bg-cyan-700 text-blue-100 rounded-full p-4">male crke</button
		>
		<p>{dolzina}/{maxDolzina}</p>
	</div>
	<div class="flex flex-wrap w-1/2 gap-1">
		{#each besedilo.split(' ') as beseda}
			<span class={nakljucnaBarva()}>{beseda}</span>
		{/each}
	</div>
</div>
