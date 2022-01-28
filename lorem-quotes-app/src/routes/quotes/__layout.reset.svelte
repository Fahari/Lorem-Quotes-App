<script>
    import Title from "$lib/title.svelte"; 
    import '../../styles/global.css';
  </script>
<header class="head">
<Title title="Quotes"/>
</header>
<main class="content">
<slot></slot>
</main>
<footer>
<p class="foot">Copyright @Kironji Kevin 2022</p>
</footer>

<style>
    .foot,
    .head{
        display: flex;
        justify-content: center;
    }
</style>