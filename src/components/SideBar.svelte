<script type="ts">
	export /**
	 * @type {{ "": string | null | undefined; }[]}
	 */
	let trendingMovies;
	const randomNum = Math.floor(Math.random() * 18);
	let data = trendingMovies[randomNum];
	console.log(data);
</script>

<div
	class="h-[100vh] shadow-[14px_3px_5px_-11px_rgba(0,0,0,0.3)] dark:shadow-none padTop fixed w-[350px] bg-slate-50 dark:bg-slate-900 border-y-0 border-r-[.2px] dark:border-slate-800"
>
	<h2 class="dark:text-slate-200 text-gray-600 text-xl ml-6 mt-8">Trending movies</h2>
	<div class="relative ml-4 mt-5 mr-5 rounded-lg">
		<img
			src={'https://image.tmdb.org/t/p/w300' + data.backdrop_path}
			alt=""
			class="rounded-lg w-full"
		/>
		<div
			class="absolute px-2 bottom-0 left-0 flex items-center right-0 backdrop-blur-[4px] bg-white/10 h-14 rounded-lg"
		>
			<div class="bg-white/30 p-1 flex items-center justify-center rounded-full">
				<ion-icon class="text-2xl text-slate-50" name="play-circle" />
			</div>
			<div class="flex">
                <div>

				<h5 class="ml-2 text-[13px] text-white mr-8">{data.original_title}</h5>
				<p class="ml-2 text-white text-[12px] pt-[.3px]">{data.release_date}</p>

                </div>
			<div class="flex absolute right-2 top-5">
				<ion-icon class="text-orange-400" name="star-outline" />
				<p class="text-white text-[12px] ">{data.vote_average.toFixed(1)}</p>
			</div>
	
			</div>
	</div>
		<div class="bottom-0 absolute top-0 w-full opacity-20 bg-orange-400 rounded-lg" />
	</div>
  <div class="w-full h-full dark:bg-slate-800">
	<h2 class="dark:text-slate-200 pt-5 text-gray-600 text-xl ml-6 mt-8 mb-3">Favourite genres</h2>

    <div class="flex mt-2 pl-5 flex-wrap">
        <a class="text-md p-1 w-24 flex hover:scale-110 mr-4 items-center justify-center rounded-lg text-slate-50 bg-orange-400" href="">Action</a>
        <a class="text-md p-1 w-28 flex hover:scale-110 mr-3  items-center justify-center rounded-lg text-slate-50 bg-orange-400" href="">Adventure</a>
        <a class="text-md p-1 w-24 flex hover:scale-110 mt-4 items-center justify-center rounded-lg mr-3 text-slate-50 bg-blue-500" href="">Western</a>
        <a class="text-md p-1 w-24 flex hover:scale-110 mt-4 items-center justify-center rounded-lg text-slate-50 bg-green-500 mr-3" href="">Western</a>
        <a class="text-md p-1 w-24 flex hover:scale-110 mr-4 items-center justify-center rounded-lg text-slate-50 bg-orange-400 mt-3 " href="">Drama</a>
        <a class="text-md p-1 w-24 flex hover:scale-110 mr-4 items-center justify-center rounded-lg text-slate-50 bg-green-500 mt-3 " href="">Drama</a>
    </div>

    <div>
       <div class="ml-5 flex mt-5 items-center">
        <span class="dark:bg-white/30 bg-slate-500 mr-2 p-1 flex items-center justify-center rounded-full">
        <ion-icon class="text-md dark:text-white" name="add"></ion-icon>
        </span>
        <span class="dark:text-white">Add your favourite genre</span>
       </div>

       <div class="flex mt-2 pl-5 flex-wrap">
        <a class="text-md hover:scale-110 p-1 w-24 flex mr-4 mt-4  items-center justify-center rounded-lg text-slate-50 bg-gray-600" href="">Crime</a>
        <a class="text-md hover:scale-110 p-1 w-24 flex mr-4 mt-4  items-center justify-center rounded-lg text-slate-50 bg-gray-600" href="">Comedy</a>
        <a class="text-md hover:scale-110 p-1 w-24 flex mr-4 mt-4  items-center justify-center rounded-lg text-slate-50 bg-gray-600" href="">Thriller</a>
       </div>
    </div>
  </div>

</div>
