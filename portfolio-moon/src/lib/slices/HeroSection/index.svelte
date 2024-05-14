<script>
import {PrismicEmbed} from '@prismicio/svelte';
import { PrismicRichText } from '@prismicio/svelte';
	import Label from './Label.svelte';

	/** @type {import("@prismicio/client").Content.HeroSectionSlice} */
	export let slice;
</script>

<header>
    <section class="scene">
        <section class="home">
            <section class="canvas">
				{@html slice.primary.spline_link.html}
                <section class="canvas-gradient">
                </section>
            </section>
        </section>
        <section class="header-intro">
            <section class="header-intro-title"> 
                <h1><PrismicRichText field={slice.primary.hero_title} /></h1>
            </section>
            <section class="header-intro-bio">
                <p><PrismicRichText field={slice.primary.hero_bio} /></p>
            </section>
        </section>
    </section>


</header>

<style>


    header {
    min-height: 100%;
    width: auto;


    align-content: center;
    align-items: center;
    display: flex;
    flex: none;
    flex-direction: column;
    flex-wrap: nowrap;
    gap: 50px;
    height: 1993px;
    justify-content: flex-start;
    overflow: visible;
    padding: 0;
    position: relative;
    width: 100%;
}

.scene {
    background-color: #F4DDE2;
    flex: none;
    height: 100vh;
    overflow: hidden;
    position: sticky;
    top: 0;
    width: 100%;
    z-index: 1;
}

.home {
    flex: none;
    inset: 0 0 0 352px;
    overflow: hidden;
    position: absolute;
}

.canvas {
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.canvas-gradient {
    background: linear-gradient(90deg,#F4DDE2 0%,rgba(240,222,226,0) 100%);
    bottom: 0;
    flex: none;
    left: 0;
    overflow: hidden;
    position: absolute;
    top: 0;
    width: 320px;
}

.header-intro {
    align-content: flex-start;
    align-items: flex-start;
    display: flex;
    flex-direction: column;
    flex-wrap: nowrap;
    gap: 20px;
    height: 90.125vh;
    justify-content: center;
    left: 279px;
    padding: 0;
    position: absolute;
    top: 0;
    width: min-content;
}

.header-intro-title {
    flex: none;
    height: auto;
    overflow: visible;
    position: relative;
    white-space: pre;
    width: auto;

    font-size: 50px;
    color: #323232;
}

.header-intro-bio {
    font-size: 20px;
    color: #323232;

    flex: none;
    height: auto;
    overflow: visible;
    position: relative;
    white-space: pre-wrap;
    width: 386px;
    word-break: break-word;
    word-wrap: break-word;
}
</style>
