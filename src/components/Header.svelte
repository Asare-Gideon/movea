<script type="ts">
	import { isDarkMood } from '../constants/store';
	let darkValue: boolean = true;
	const handleDarkTheme = () => {
		darkValue = !darkValue;
		isDarkMood.set(darkValue);
	};
</script>

<div
	class="header dark:border-x-0 dark:border-t-0 dark:border-b-[.1px] dark:border-gray-800 fixed flex bg-slate-50 z-40 justify-between dark:bg-gray-900 items-center px-4 w-full h-[4rem] shadow-[0_5px_5px_-5px_rgba(0,0,0,0.3)]"
>
	<div class="flex">
		<h1 class="dark:text-slate-200 text-3xl">MOVEA</h1>
		<ion-icon class="text-orange-500" name="bonfire" />
	</div>
	<div class="nav-item">
		<ul class="flex relative nav-list">
			<li><a class="text-lg dark:text-slate-100 mx-3" href="#">Movies</a></li>
			<li><a class="text-lg dark:text-slate-100 mx-3" href="#">TV shows</a></li>
			<li><a class="text-lg dark:text-slate-100 mx-3" href="#">Animations</a></li>
			<li><a class="text-lg dark:text-slate-100 mx-3" href="#">Up coming</a></li>
		</ul>
	</div>
	<div class="flex ">
		<a on:click={handleDarkTheme} href="#" class="mx-3"
			><ion-icon class="text-gray-600 dark:text-slate-200 text-3xl" name={$isDarkMood?"sunny" :'moon'} /></a
		>
		<a href="#" class="mx-3"><ion-icon class="text-gray-600 dark:text-slate-200 text-3xl" name="search" /></a>
		<a href="#" class="mx-3"><ion-icon class="text-gray-600 dark:text-slate-200 text-3xl" name="grid" /></a>
		<a href="#" class="mx-3"><ion-icon class="text-gray-600 dark:text-slate-200 text-3xl" name="contact" /></a>
	</div>
</div>
