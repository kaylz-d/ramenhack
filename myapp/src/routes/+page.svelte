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
    import ramenbowl from '$lib/assets/ramenbowl.png';

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

        ScrollTrigger.create({
            trigger: '#what',
            start: 'top center',
            end: 'bottom center',
            toggleClass: {
                targets: '#what-text',
                className: '!text-red-600'
            }
        }),

        ScrollTrigger.create({
            toggleClass: {
                targets: '#hello-text',
                className: '!text-orange-400'
            }
        }),

        gsap.to('#bowl', {
            scrollTrigger: {
                trigger: '#what',
                start: 'top bottom',
                end: 'bottom top',
                scrub: true
            },
            rotation: -90,
            ease: 'none'
        })
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

<div class="bg-[#FFCC90] w-screen h-screen">
	<!-- #FFCC90 is a good color -->
	<div
		style="background-image: url({wallpaper})"
		class="inset-0 flex h-screen w-screen flex-col items-center justify-center bg-cover bg-center font-[Belanosima]"
	>
		<div class="fixed text-lg lg:text-2xl text-red-500 right-0 my-auto text-center pr-4 lg:pr-8">
            <p id="hello-text">hello</p>
            <p id="what-text" class="text-orange-400">what?</p>
            <p class="text-orange-400">FAQ</p>
            <p class="text-orange-400">guides</p>
        </div>
        <img src={title} alt="Ramen Hack title" class="my-4 max-h-[30vh] w-auto" />
		<div class="flex flex-col items-center justify-center gap-3 lg:flex-row">
			<p class="text-lg text-red-500">use cool scrolling effects</p>
			<button
				class="rounded-full border-2 border-red-500 px-4 py-2 text-lg text-red-500 hover:bg-red-500 hover:text-white"
				>• SUBMIT HERE •</button
			>
			<p class="text-lg text-red-500">get a grant to buy noodles</p>
		</div>

		<!-- <div id="book">
        
    </div> -->
	</div>

	<img
		src="https://assets.hackclub.com/flag-orpheus-top.svg"
		alt="Hack Club flag that links to Hack Club website"
		class="fixed top-0 left-0"
	/>

    <!-- <img src={ramenbowl} alt="Picture of ramen bowl" class="hidden lg:block fixed -left-80 -bottom-110 scale-75 rotate-75"> -->
    <div id="what" class="bg-[#FFCC90] w-screen h-screen flex flex-col items-center justify-center">
        <p class="text-4xl bold font-[Belanosima] py-8 text-red-500">How does this work?</p>
        <img id="bowl" src={ramenbowl} alt="Tonkotsu ramen" class="h-100 w-auto rotate-75">
        <p class="text-2xl bold font-[Belanosima] py-8">More stuff to come later :D</p>
    </div>
</div>
