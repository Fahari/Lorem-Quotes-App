<script context="module">
  export async function load({ fetch }) {
    const res = await fetch("https://jsonplaceholder.typicode.com/posts");
    const quotes = await res.json();

    if (res.ok) {
      return {
        props: {
          quotes,
        },
      };
    }
    return {
      status: res.status,
      error: new Error("could not fetch quotes"),
    };
  }
</script>

<script>
  export let quotes;
</script>

<div class="quote">
  <p>
    Lorem ipsum dolor sit amet consectetur adipisicing elit. Dolore ipsum harum
    ex repellendus aut enim, voluptates, veritatis, eligendi quas facilis
    voluptatem. Quis, impedit sapiente. Ut asperiores natus voluptates fugiat
    libero! Numquam similique illum, incidunt laborum, recusandae explicabo
    laudantium excepturi earum fugit iure deleniti quo doloremque reprehenderit
    eaque magni, eum nobis. Ipsum iusto voluptatum in modi.
  </p>
  <ul>
      {#each quotes as quote}
        <li><a sveltekit:prefetch href={`/quotes/${quote.id}`}>{quote.title}</a></li>
      {/each}
  </ul>
  <p><a href="/about">About Us</a></p>
  <p><a href="/">Home</a></p>
</div>

<style>
  .quote {
    width: 80%;
    text-align: center;
    display: block;
    margin: 2em auto;
  }
  p:first-child {
    text-align: justify;
    text-justify: inter-word;
  }
  ul{
      text-align: start;
  }
  a {
    display: inline-block;
    margin-top: 0.5rem;
    padding: 0.8em;
    /* border: 1px solid rgba(255, 255, 255, 0.2); */
    border-radius: 2%;
  }
</style>
