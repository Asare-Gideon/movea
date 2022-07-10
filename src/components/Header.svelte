<script type="ts">
	import { isDarkMood } from '../constants/store';
	let darkValue: boolean = true;
	const handleDarkTheme = () => {
		darkValue = !darkValue;
		isDarkMood.set(darkValue);
	};

	let navData = [
		{
			id: '1',
			name: 'Movies',
			selected: true
		},
		{
			id: '2',
			name: 'TV shows',
			selected: false
		},
		{
			id: '3',
			name: 'Animation',
			selected: false
		},
		{
			id: '4',
			name: 'Up coming',
			selected: false
		}
	];

	const handleNav = (id: string) => {
		const newNaveData = navData.map((item) => {
			if (id === item.id) {
				return {
					...item,
					selected: true
				};
			} else {
				return {
					...item,
					selected: false
				};
			}
		});
		navData = newNaveData;
	};
</script>

<div
	class="header dark:border-x-0 dark:border-t-0 dark:border-b-[.1px] dark:border-gray-800 fixed flex bg-slate-50 z-40 justify-between dark:bg-gray-900 items-center px-4 w-full h-[4rem] shadow-[0_5px_5px_-5px_rgba(0,0,0,0.3)]"
>
	<div class="flex">
		<h1 class="dark:text-slate-200 text-3xl ml-2 cursor-pointer">MOVEA</h1>
		<ion-icon class="text-orange-500" name="bonfire" />
	</div>
	<div class="nav-item">
		<ul
			class={`flex relative nav-list ${navData[0].selected ? 'before:left-[25px]' : ''} ${
				navData[1].selected ? 'before:left-[7.8rem]' : ''
			} ${navData[2].selected ? 'before:left-[14.8rem]' : ''} ${
				navData[3].selected ? 'before:left-[22rem]' : ''
			}`}
		>
			{#each navData as nav}
				<li on:click={() => handleNav(nav.id)} class="hover:scale-110" >
					<a class="text-lg dark:text-slate-100 mx-6" href="#">{nav.name}</a>
				</li>
			{/each}
		</ul>
	</div>
	<div class="flex ">
		<a on:click={handleDarkTheme} href="#" class="mx-2 md:mx-3 group"
			><ion-icon
				class="text-gray-600 dark:text-slate-200 text-3xl group-hover:text-orange-500"
				name={$isDarkMood ? 'sunny' : 'moon'}
			/></a
		>
		<a href="#" class="mx-2 md:mx-3 group"
			><ion-icon class="text-gray-600 dark:text-slate-200 text-3xl group-hover:text-orange-500" name="search" /></a
		>
		<a href="#" class="mx-2 md:mx-3 group"
			><ion-icon class="text-gray-600 dark:text-slate-200 text-3xl group-hover:text-orange-500" name="grid" /></a
		>
		<a href="#" class="mx-2 md:mx-3 group"
			><ion-icon class="text-gray-600 dark:text-slate-200 text-3xl group-hover:text-orange-500" name="contact" /></a
		>
	</div>
</div>
