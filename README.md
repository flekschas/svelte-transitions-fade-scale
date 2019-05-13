# svelte-transitions-fade-scale

A transition plugin for [Svelte](https://svelte.dev) that fades and scales in an element in parallel. [Demo](https://svelte.dev/repl/de8970d53ce040159aba167c0a4af6ef?version=3.2.2)

![fade-scale](https://user-images.githubusercontent.com/932103/57627484-1458f900-7566-11e9-9294-edb3f1bd2529.gif)

## Usage

Recommended usage is via [svelte-transitions](https://github.com/sveltejs/svelte-transitions), but you can use this module directly if you prefer. Note that it assumes an ES module or CommonJS environment.

Install with npm or yarn:

```bash
npm install --save svelte-transitions-fade-scale
```

Then add the plugin to your Svelte component's exported definition:

```html
<script>
  import fadeScale from 'svelte-transitions-fade-scale';

  let visible = false;
</script>

<label>
  <input type='checkbox' bind:checked={visible}> visible
</label>

{#if visible}
  <!-- use `in`, `out`, or `transition` (bidirectional) -->
  <div transition:fadeScale>hello!</div>
{/if}
```


## Parameters

You can specify `delay`, `duration`, `easing`, and `baseScale` parameters, which default to `0`, `400`, `x => sx`, and `0` repectively:

```html
<script>
  import { cubicInOut } from 'svelte/easing';
</script>

<div
  in:fadeScale={{
    delay: 250,
    duration: 1000,
    easing: cubicInOut,
    baseScale: 0.5
  }}
>
  fades and scales in slowly from 0 opacity and 0.5 scaling after a short delay with cubic easing
</div>
```


## License

[MIT](LICENSE)
