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
					<script type="module" src="https://unpkg.com/@splinetool/viewer@1.3.5/build/spline-viewer.js"></script>
					<spline-viewer loading-anim-type="spinner-small-dark" url="https://prod.spline.design/M5QYIxncM4JfLx4i/scene.splinecode"></spline-viewer>
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
    gap: 30px;
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

@media (min-width: 810px) and (max-width: 1199px) {

.scene {
    bottom: unset;
    height: 105vh;
    left: 0;
    right: unset;
    width: 100%;
}

.home {
    flex: none;
    inset: 0 0 0 0px;
    overflow: hidden;
    position: absolute;
}

.canvas {
    top: 0px;
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.canvas-gradient {
    background: linear-gradient(180deg,#f9dce2 0%,rgba(240,222,226,0) 100%);
    bottom: unset;
    height: 300px;
    right: 0;
    width: unset;
}

.header-intro {
    align-content: center;
    align-items: center;
    height: min-content;
    left: 50%;
    top: 50px;
    transform: translate(-50%);
    text-align: center;
}

.header-intro-title {
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    flex-shrink: 0;
    transform: none;

}

.header-intro-bio {
    outline: none;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    flex-shrink: 0;
    transform: none;
}
    
}

@media (max-width: 810px) {
    .scene {
    bottom: unset;
    height: 105vh;
    left: 0;
    right: unset;
    width: 100%;
}

.home {
    flex: none;
    inset: 0 0 0 0px;
    overflow: hidden;
    position: absolute;
}

.canvas {
    top: 0px;
    width: 100%;
    height: 100%;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
}

.canvas-gradient {
    background: linear-gradient(180deg,#f9dce2 0%,rgba(240,222,226,0) 100%);
    bottom: unset;
    height: 300px;
    right: 0;
    width: unset;
}

.header-intro {
    align-content: center;
    align-items: center;
    height: min-content;
    left: 50%;
    top: 50px;
    transform: translate(-50%);
    text-align: center;

    font-size: 26px;
}

.header-intro-title {
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    flex-shrink: 0;
    transform: none;

    font-size: 36px;

}

.header-intro-bio {
    outline: none;
    display: flex;
    flex-direction: column;
    justify-content: flex-start;
    flex-shrink: 0;
    transform: none;
}
}



</style>
