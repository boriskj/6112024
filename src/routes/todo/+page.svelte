<script lang="ts">
	type Task = {
		text: string;
		status: boolean;
	};

	let newTask: string = '';

	let tasks: Task[] = [
		{
			text: 'skuham kosilo',
			status: false
		},
		{
			text: 'pomij posodo',
			status: true
		},
		{
			text: 'igraj igrice',
			status: true
		},
		{
			text: 'pospravi perilo',
			status: false
		},
		{
			text: 'uci se',
			status: false
		}
	];
	function add() {
		tasks = [...tasks, { text: newTask, status: false }];
		newTask = '';
	}
</script>

<div class="flex justify-center">
	<div class=" rounded-2xl bg-cyan-700 m-4 p-4">
		<div class="flex gap-2">
			<input bind:value={newTask} class="rounded-full px-4" type="text" />
			<button on:click={add} class="bg-blue-100 rounded-full px-4">dodaj zadolžitev</button>
		</div>

		<h3 class="text-2xl">to nared</h3>
		{#each tasks as task}
			<p
				class={task.status
					? 'text-black bg-blue-100 rounded-full m-2 p-2'
					: 'text-blue-100 m-2 p-2'}
			>
				<button on:click={() => (task.status = !task.status)}>{task.status ? '☑️' : '❌'}</button
				>{task.text}
			</p>
		{/each}
	</div>
</div>
