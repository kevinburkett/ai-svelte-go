<script lang="ts">
import MdHome from 'svelte-icons/md/MdHome.svelte';
import MdInfo from 'svelte-icons/md/MdInfo.svelte';
import MdContactMail from 'svelte-icons/md/MdContactMail.svelte';

const items = [
  { href: '/', label: 'Home', icon: MdHome },
  { href: '/about', label: 'About', icon: MdInfo },
  { href: '/contact', label: 'Contact', icon: MdContactMail }
];
</script>

<nav class="sidebar">
  {#each items as item}
    <a class="nav-item" href={item.href}>
      <svelte:component this={item.icon} class="icon" />
      <span>{item.label}</span>
    </a>
  {/each}
</nav>

<style>
.sidebar {
  position: fixed;
  top: 0;
  left: 0;
  bottom: 0;
  width: 60px;
  background-color: #333;
  color: white;
  transition: width 0.2s ease;
  overflow-x: hidden;
  display: flex;
  flex-direction: column;
}
.sidebar:hover {
  width: 200px;
}
.nav-item {
  display: flex;
  align-items: center;
  padding: 1rem;
  text-decoration: none;
  color: inherit;
}
.icon {
  width: 24px;
  height: 24px;
}
.nav-item span {
  margin-left: 1rem;
  white-space: nowrap;
  opacity: 0;
  transition: opacity 0.2s ease;
}
.sidebar:hover .nav-item span {
  opacity: 1;
}
</style>
