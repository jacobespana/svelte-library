<script>
    import Button from "../common/Button.svelte";
    import BookGrid from "../common/BookGrid.svelte";
    import { httpGet } from '../common/api.js';
    import { onMount } from 'svelte';

    export let onBookSelect;

    let books = [];

    onMount(async function () {
      const { data } = await httpGet("/?_sort=id&_order=desc");
      books = data;
    });

</script>

<header>
    <span class="preamble">Welcome to the</span>
    <h1>Library</h1>
</header>

<p class="greeting">
    This is a library for the people. Welcome. Read the books here. Be inspired.
    Go home, and share them with your family.
</p>

<Button>+ Add Book</Button>

<BookGrid books={books} {onBookSelect} />
<style>
    header {
        margin: var(--spacingMedium) 0 var(--spacingLarge) 0;
        text-transform: uppercase;
    }
    .preamble {
        display: block;
    }
    h1 {
        font-size: var(--typeSizeXXLarge);
        font-weight: var(--typeWeightBold);
        line-height: var(--typeLineHeightTight);
    }

    .greeting {
        font-size: var(--typeSizeSmall);
    }
</style>
