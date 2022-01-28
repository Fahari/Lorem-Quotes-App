<script context="module">
  export async function load({ fetch, params }) {
    const id = params.id;
    const res = await fetch(`https://jsonplaceholder.typicode.com/posts/${id}`);
    const quote = await res.json();
    console.log(quote);

    if (res.ok) {
      return {
        props: {
          quote,
        },
      };
    }
    return {
      status: 301,
      //   error: new Error("COULD NOT FETCH quoteS"),
      redirect: "/quotes",
    };
  }
</script>

<script>
  export let quote;
</script>

<div class="quote">
  <h2>{quote.title}</h2>
  <p>{quote.body}</p>
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
</style>
