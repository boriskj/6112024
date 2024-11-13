<script lang="ts">
	type Operator = '+' | '-' | '*' | '/';
	let num1 = 0;
	let num2 = 0;
	let op: Operator = '+';
	let result = 0;
	$: {
		if (op === '+') {
			result = num1 + num2;
		} else if (op === '-') {
			result = num1 - num2;
		} else if (op === '*') {
			result = num1 * num2;
		} else if (op === '/') {
			result = num1 / num2;
		}
	}
	function randomNumber() {
		num1 = Math.floor(Math.random() * 100);
		num2 = Math.floor(Math.random() * 100);
	}
</script>

<div class="p-4">
	<h1 class="text-4xl">kalkulator</h1>
	<div class="flex gap-10 justify-center">
		<input
			bind:value={num1}
			type="number"
			placeholder="0"
			class="border-4 rounded-sm border border-cyan-700"
		/>

		<input
			bind:value={num2}
			type="number"
			placeholder="0"
			class="border-4 rounded-sm border border-cyan-700"
		/>
		<select bind:value={op} class="border-4 rounded-sm border border-cyan-700">
			<option value="+"> + </option>
			<option value="-"> - </option>
			<option value="*"> * </option>
			<option value="/"> / </option>
		</select>
		<button
			on:click={randomNumber}
			class="bg-cyan-700 w-7
    h-7
    rounded-full"
		>
			?</button
		>
	</div>
	<div class="flex gap-4 flex-row justify-center">
		<p class="text-8xl">{num1} {op} {num2} = {result}</p>
	</div>
</div>
