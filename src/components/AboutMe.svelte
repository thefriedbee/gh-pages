<script>
  import myphoto from '../assets/img/my-img.jpeg'
  // a paragraph explaining the content of the paper (could be the abstract)
  export let activeLang;
</script>


<div class="about-me">
  <div class="image">
    <img src={myphoto} class="img-fluid" alt="My Selfie">
  </div>
  <div class="info-lang">
    {#if activeLang == "English"}
    <h2 id="Bio">Diyi Liu</h2>
    <ul class="list-unstyled">
      <li>Currently Postdoc at the George Washington University</li>
      <li>Ph.D in Transportation Engineering at University of Tennessee, Knoxville</li>
    </ul>
    {:else if activeLang == "中文"}
    <h2 id="Bio">刘迪一</h2>
    <ul class="list-unstyled">
      <li>乔治华盛顿大学 (George Washington University) 交通工程专业博士后</li>
      <li>田纳西大学, 诺克斯维尔分校(UT, Knoxville)交通工程专业博士</li>
    </ul>
    {/if}
  </div>
</div>

<hr class="custom-hr">

<style>
  /* Add your CSS styles for the PaperCard component here */
  .about-me {
    display: flex;
    flex-direction: row;
    margin: 20px;
    margin-left: 20px;
    padding: 10px;
    border-radius: 5px;
  }

  h2 {
    font-weight: bold;
  }

  /* Media query for narrow screens (e.g., mobile) */
  @media (max-width: 768px) {
    .about-me {
      flex-direction: column;
      margin-left: 20px;
    }
  }

  .info-lang {
    flex: 3;
	  flex-direction: row;
    margin-left: 20px;
  }

  .image {
    flex: -1; /* Move image to the top */
    max-width: 120px;
    min-width: 120px;
    margin: 10px;
    margin-left: -10px;
  }
  
  .custom-hr {
    margin-top: 5px;
    margin-bottom: 5px;
    border: 0;
    border-top: 1px solid rgba(0, 0, 0, 0.1);
    width: 95%;
  }
</style>
  