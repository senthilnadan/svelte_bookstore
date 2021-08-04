<script>
    import { onMount } from "svelte";
    import Button from "../common/button.svelte"
    import BookGrid from "../lib/bookgrid.svelte";
    import { httpGet } from "../common/bookapi.js";

  let books = [];
  onMount(async function() {
    const { data } = await httpGet("/?_sort=id&_order=desc");
    books = data;
  });
</script>
<h1>Welcome to Our Bookstore</h1>
<p>Visit <a href="https://kit.svelte.dev">kit.svelte.dev</a> to read the documentation</p>

<Button>+ Add Book</Button>

<BookGrid {books} />