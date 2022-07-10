<script context="module">
	import { dataset_dev } from 'svelte/internal';

	//@ts-ignore
	export const load = async ({ fetch }) => {
		const res = await fetch(
			`https://api.themoviedb.org/3/trending/all/day?api_key=733a043e6cd9af9cf7893dca67f65fc5`
		);

		if (res.ok) {
			const data = await res.json();
			return {
				props: { trendingMovies: data.results }
			};
		} else {
			return {
				status: res.status,
				err: new Error("couldn't get data")
			};
		}
	};
</script>

<script>
	export /**
* @type {any}
*/
	 let trendingMovies;
	import '../global.css';
	import Header from '../components/Header.svelte';
	import { isDarkMood } from '../constants/store';
	import SideBar from '../components/SideBar.svelte';

</script>

<div class={`w-full ${$isDarkMood ? 'dark' : ''}`}>
	<div class="dark:bg-gray-900 bg-slate-50 w-full h-full">
		<Header />
		<SideBar {trendingMovies} />

		<div class="ml-[350px]">
			<slot />
		</div>
	</div>
</div>
