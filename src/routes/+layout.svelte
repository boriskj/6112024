<script lang="ts">
	import { page } from '$app/stores';
	import '../app.css';

	function bold(link: string) {
		if (link === $page.url.pathname) {
			return 'font-bold';
		} else {
			return '';
		}
	}
</script>

<nav class="w-full p-6 bg-cyan-700">
	<div class="flex gap-4">
		<a href="/" class={$page.url.pathname === '/' ? 'font-bold' : ''}>Gumb</a>
		<a href="/domov" class={$page.url.pathname === '/domov' ? 'font-bold' : ''}>Domov</a>
		<a href="/trgovina" class={$page.url.pathname === '/trgovina' ? 'font-bold' : ''}>Trgovina</a>
		<a href="/kalkulator" class={$page.url.pathname === '/kalkulator' ? 'font-bold' : ''}
			>Kalkulator</a
		><a href="/todo" class={$page.url.pathname === '/todo' ? 'font-bold' : ''}>Zadolžitve</a>
		<a href="/stevila" class={$page.url.pathname === '/stevila' ? 'font-bold' : ''}>Števila</a>
		<a href="/posts" class={$page.url.pathname === '/posts' ? 'font-bold' : ''}>Objave</a>
	</div>
</nav>

<div class="w-full h-screen bg-blue-100">
	<slot />
</div>
