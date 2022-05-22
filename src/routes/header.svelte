<script context="module" lang="ts">
	export const prerender = true;
    import { page } from '$app/stores';
</script>

<div class="header">
    <a class='header-but' sveltekit:prefetch href="/gameset">Кнопка</a>
    <a class='header-but' sveltekit:prefetch href="/gameplay/gameplay">Кнопка</a>
    <span class='header-but'>Кнопка</span>
    <span class='header-but'>Кнопка</span>
</div>

<style>
    a {
        text-decoration: none;

    }
</style>