<script>
import Sidebar from '$lib/Sidebar.svelte';
</script>

<Sidebar />
<main>
  <slot />
</main>

<style>
main {
  margin-left: 60px;
  padding: 1rem;
  transition: margin-left 0.2s ease;
}
.sidebar:hover + main {
  margin-left: 200px;
}
</style>
