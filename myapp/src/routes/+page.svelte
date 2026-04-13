<!-- <h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the documentation</p>
<p class="text-5xl font-bold text-blue-600">Just a test to see how this works! :D</p> -->

<script lang="ts">
	// this part is vibecoded because i didn't use a boilerplate
	import { onMount } from 'svelte';
	import { gsap } from 'gsap';
	import { ScrollTrigger } from 'gsap/dist/ScrollTrigger';
	import Lenis from 'lenis';
    import title from '$lib/assets/title.png';
    import wallpaper from '$lib/assets/background_reexport.png';

	onMount(() => {
		// gemini says onMount is used to wait for the page to load before starting GSAP
		// becuz gsap needs to find book element in HTML
		const lenis = new Lenis();
		function raf(time: number) {
			lenis.raf(time);
			requestAnimationFrame(raf);
		}
		requestAnimationFrame(raf);
		gsap.registerPlugin(ScrollTrigger);
		// put book animation here

        // AI GENERATED CODE, just using for reference==============
		// gsap.to('#book', {
		// 	scrollTrigger: {
		// 		trigger: '.h-\\[400vh\\]', // The long scroll track
		// 		start: 'top top', // Start when the top of the track hits the top of the screen
		// 		end: 'bottom bottom', // End when the bottom hits the bottom
		// 		scrub: 1 // 1 second "catch up" - makes it feel smooth
		// 	},
		// 	rotationY: -180, // Flips the book over
		// 	x: -100, // Moves it slightly left like a real book opening
		// 	ease: 'none' // No bounce, just direct scroll-to-animation mapping
		// });
	});
</script>

<!-- ======AI GENERATED CODE, only use for reference========== -->
<!-- <div class="fixed inset-0 flex items-center justify-center bg-stone-200">
  <div id="book" class="w-64 h-96 bg-white shadow-2xl flex items-center justify-center border-l-8 border-amber-900">
    <p class="font-serif italic text-stone-800">My Story Begins...</p>
  </div>
</div> -->

<!-- The Scroll Track: This creates the "length" of the scroll -->
<!-- <div class="h-[400vh]"></div> -->

<!-- #FFCC90 is a good color -->
<div style="background-image: url({wallpaper})" class="font-[Belanosima] fixed inset-0 flex flex-col items-center justify-center bg-cover bg-center">
    <img src={title} alt="Ramen Hack title" class="max-h-[30vh] w-auto my-4">
    <div class="flex flex-col lg:flex-row items-center justify-center gap-3">
        <p class="text-red-500 text-lg">use cool scrolling effects</p>
        <button class="text-red-500 text-lg border-2 border-red-500 rounded-full py-2 px-4 hover:text-white hover:bg-red-500">• RSVP HERE •</button>
        <p class="text-red-500 text-lg">get a grant to buy noodles</p>
    </div>

    <div id="book">
        
    </div>
</div>

<img src="https://assets.hackclub.com/flag-orpheus-top.svg" alt="Hack Club flag that links to Hack Club website" class="fixed top-0 left-0">