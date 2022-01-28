<script context="module">
    export function load({ error }) {
      return {
        props: { message: error.message },
      };
    }
  </script>
  
  <script>
    export let message;
  </script>
  
  <div class="error">
    <h2>Oh No!! What you're looking for doesn't exist!</h2>
    <p>{message}</p>
    <a href="/quotes">Go back to Quotes...</a>
  </div>
  
  <style>
    .error {
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
  