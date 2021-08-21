<script>
	import Navbar from './layout/Navbar.svelte';
	import Sidebar from './layout/Sidebar.svelte';
	import Home from './pages/home/home.svelte';

	let open = false
</script>

<div class="app ">
	<div class="container">
		<Navbar bind:sidebar={open}/>
		<Home />
	</div>
	<Sidebar bind:open/>
</div>

<style>
	.app {
		display: flex;
		justify-content: center;
		max-width: 1280px;
	}
	.container {
		padding: 2rem;
	}
</style>
