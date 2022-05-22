<script context="module" lang="ts">
	export const prerender = true;
    import { page } from '$app/stores';
</script>

<div class="header">
    <a class='header-but' sveltekit:prefetch href="/gameset">Кнопка 1</a>
    <a class='header-but' sveltekit:prefetch href="/gameplay/gameplay">Кнопка 2</a>
    <span class='header-but'>Кнопка 3</span>
    <span class='header-but'>Кнопка 4</span>
</div>

<style>
    a {
        text-decoration: none;

    }
</style>