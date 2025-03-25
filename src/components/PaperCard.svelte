<script>
  export let imageSrc = '';
  export let videoSrc = '';
  export let title = '';
  // weblink creates a separate link that explains the paper
  export let links = {};

  // import github_badge from '../assets/badge/github_badge.svg';
  // import github_badge from "https://img.shields.io/badge/code-github-green"
  // Optional badge URLs keyed by link type
  let badges = {
    "GitHub": "https://img.shields.io/badge/code-github-green",
    "Paper": "https://img.shields.io/badge/paper-red",
    "Report": "https://img.shields.io/badge/report-blue",
    "App": "https://img.shields.io/badge/app-yellow"
  };

  let badges_cn = {
    "GitHub": "https://img.shields.io/badge/代码-github-green",
    "Paper": "https://img.shields.io/badge/论文-red",
    "Report": "https://img.shields.io/badge/报告-blue",
    "App": "https://img.shields.io/badge/应用-yellow"
  };

  export let summary = '';
  export let activeLang = 'English';

  const cn_map = {
    "Paper": "论文",
    "GitHub": "代码网址",
    "Slides": "幻灯片",
    "App": "应用",
    "Report": "报告"
  }

  if (activeLang === "中文") {
    badges = badges_cn;
  }
</script>


<div class="paper-card">
<div class="image">
  {#if videoSrc}
    <div class="video-container">
      <video autoplay loop muted playsinline>
        <source src={videoSrc} type="video/gif">
      </video>
    </div>
  {:else}
    <img src={imageSrc} alt={title} style="width: 100%; height: auto;"/>
  {/if}
</div>
<div class="info">
  <h4>{title}<p class="links">
    {#each Object.entries(links) as [name, page], i}
      <span class="link-item">
        {#if badges[name]}
          <a href={page} target="_blank" rel="noopener noreferrer">
            <img src={badges[name]} alt={activeLang === "中文" ? cn_map[name] || name : name}/>
          </a>
        {:else}
          {#if activeLang === "中文"}
            <a href={page} target="_blank" rel="noopener noreferrer">{cn_map[name] || name}</a>
          {:else}
            <a href={page} target="_blank" rel="noopener noreferrer">{name}</a>
          {/if}
        {/if}
        <!-- {#if i < Object.keys(links).length - 1}<span class="separator">|</span>{/if} -->
      </span>
    {/each}
  </p></h4>
  {#if activeLang == "English"}
    <p><span class="text-danger">Summary: </span> {summary}</p>
  {:else}
    <p><span class="text-danger">摘要: </span> {summary}</p>
  {/if}
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

  .video-container {
    position: relative;
    width: 100%;
    padding-bottom: 56.25%; /* For 16:9 aspect ratio */
  }
  
  video {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
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

  .links {
    display: flex;
    flex-wrap: wrap;
    align-items: center;
    gap: 5px;
  }

  .separator {
    margin: 0 5px;
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
