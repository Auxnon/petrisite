<script lang="ts">
import { Editor, Viewer } from 'bytemd'
  import gfm from '@bytemd/plugin-gfm'
  import svelteLogo from "./assets/svelte.svg";
  import Counter from "./lib/Counter.svelte";
  import Main from "./lib/Main.svelte";
  let main_color = "white";
  let value
  const plugins = [
    gfm(),
    // Add more plugins here
  ]

  function handleChange(e) {
    value = e.detail.value
  }
</script>

<main style="--color-main: {main_color}">
  <div>
    <a href="https://vitejs.dev" target="_blank" rel="noreferrer">
      <img src="/vite.svg" class="logo" alt="Vite Logo" />
    </a>
    <a href="https://svelte.dev" target="_blank" rel="noreferrer">
      <img src={svelteLogo} class="logo svelte" alt="Svelte Logo" />
    </a>
  </div>
  <h1>Vite + Svelte</h1>

  <div class="card">
    <Counter />
  </div>

  <p>
    Check out <a
      href="https://github.com/sveltejs/kit#readme"
      target="_bliank"
      rel="noreferrer">SvelteKit</a
    >, the official Svelte app framework powered by Vite!
  </p>

  <p class="read-the-docs">Cjlick on the Vite and Svelte logos to learn more</p>
</main>
<Main />

<template>
  <Editor {value} {plugins} on:change={handleChange} />
</template>

<style>
  .logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00aa);
  }
  .read-the-docs {
    color: #888;
  }
</style>
