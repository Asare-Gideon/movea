<script>
    import "../global.css"
    import Header from '../components/Header.svelte'
    import {isDarkMood} from '../constants/store'

    console.log(isDarkMood)
</script>


<div class={`w-full ${$isDarkMood? 'dark': ''}`}>
<div class="dark:bg-gray-900 bg-slate-50 w-full h-full">
<Header />
 <slot />
</div>

</div>