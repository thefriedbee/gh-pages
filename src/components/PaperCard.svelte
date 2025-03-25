<script>
  export let imageSrc = '';
  export let title = '';
  // weblink creates a separate link that explains the paper
  export let links = {};

  // a paragraph explaining the content of the paper (could be the abstract)
  export let summary = '';
</script>


<div class="paper-card">
<div class="image">
  <img src={imageSrc} alt={title} />
</div>
<div class="info">
  <h4>{title}</h4>
  <p>
    {#each Object.entries(Object.entries(links)) as [i, [name, page]]}
      <a href={page} target="_blank" rel="noopener noreferrer">{name}</a>
      {#if Number(i) < Object.keys(links).length - 1}|&nbsp
      {/if}
    {/each}
  </p>
  <p><span class="text-danger">Summary: </span> {summary}</p>
</div>
</div>

<style>
  /* Add your CSS styles for the PaperCard component here */
  .paper-card {
    display: flex;
    margin: 5px;
    padding: 10px;
    border: 1px solid #ddd;
    border-radius: 5px;
  }

  .image {
    flex: 1;
    max-height: 500px;
  }

  .image img {
    max-width: 100%;
    height: auto;
  }

  .info {
    flex: 3;
    padding-left: 20px;
  }

  h4 {
    font-size: 1.0rem;
    margin-top: 0;
  }

  a {
    text-decoration: none;
    color: #0070f3;  /* Link color can be customized */
  }

  /* Media query for narrow screens (e.g., mobile) */
@media (max-width: 768px) {
  .paper-card {
    flex-direction: column; /* Stack elements vertically */
  }

  .image {
    flex: -1; /* Move image to the top */
    margin-bottom: 5px; /* Add space between image and content */
  }

  .info {
    padding-left: 0; /* Reset padding for content */
  }
}
</style>
