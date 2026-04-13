<!-- <h1>Welcome to SvelteKit</h1>
<p>Visit <a href="https://svelte.dev/docs/kit">svelte.dev/docs/kit</a> to read the documentation</p>
<p class="text-5xl font-bold text-blue-600">Just a test to see how this works! :D</p> -->

<script lang="ts">
    // this part is vibecoded because i didn't use a boilerplate
    import { onMount } from 'svelte';
    import { gsap } from 'gsap';
    import { ScrollTrigger } from 'gsap/dist/ScrollTrigger';
    import Lenis from 'lenis';

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
        // put book animation here later
    })
</script>