---
title: "Code"
description: "Github Repos & Codebase for Personal Projects"
# 1. To ensure Netlify triggers a build on our exampleSite instance, we need to change a file in the exampleSite directory.
theme_version: '2.8.2'
layout: about_me
cascade:
  featured_image: "/images/baja_water/cacti_sunset.jpg"
---
<style>
  .projects-container {
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    gap: 20px;
    margin: 20px;
  }

  .project-card {
    border: 1px solid #ddd;
    border-radius: 8px;
    padding: 15px;
    text-align: center;
    box-shadow: 2px 2px 10px rgba(0, 0, 0, 0.1);
    background-color: #f9f9f9;
    transition: transform 0.2s ease, box-shadow 0.2s ease;
  }

  .project-card:hover {
    transform: scale(1.05);
    box-shadow: 4px 4px 15px rgba(0, 0, 0, 0.2);
  }

  .project-image {
    width: 100%;
    height: 150px;
    object-fit: cover;
    border-radius: 8px;
  }

  .project-image-bottom {
    width: 100%;
    height: 150px;
    object-fit: cover;
    border-radius: 8px;
    object-position: bottom center;
  }

  .project-title {
    font-size: 1.2rem;
    margin: 10px 0;
    font-weight: bold;
  }

  .project-tags {
    margin: 10px 0;
    font-size: 0.9rem;
    color: #555;
  }

  .project-link {
    display: inline-block;
    margin-top: 10px;
    padding: 8px 12px;
    background-color: #007bff;
    color: white;
    border-radius: 4px;
    text-decoration: none;
  }

  .project-link:hover {
    background-color: #0056b3;
  }

  .tags-list {
    list-style: none;
    padding: 0;
  }

  .tag-item {
    display: inline-block;
    margin: 2px;
  }

  .tag-link {
    font-size: 0.9rem;
    display: inline-block;
    padding: 5px 10px;
    border-radius: 20px;
    border: 1px solid #007bff;
    color: #007bff;
    text-decoration: none;
    transition: background-color 0.2s, color 0.2s;
  }

  .tag-no-link {
    font-size: 0.9rem;
    display: inline-block;
    padding: 5px 10px;
    border-radius: 20px;
    border: 1px solid #007bff;
    color: #007bff;
    text-decoration: none;
    transition: background-color 0.2s, color 0.2s;
  }

  .tag-link:hover {
    background-color: #007bff;
    color: white;
  }
</style>


<div class="projects-container">

  <div class="project-card">
    <img src="/blog/images/alaska_coast.jpg" alt="water-db-image" class="project-image">
    <h3 class="project-title">water-doc-db</h3>
    <p>Example workflow of vector database ingest and Gen AI query with water policy docs.</p>
    <li class="tag-item">
        <a class="tag-no-link">LLMs</a>
    </li>
    <li class="tag-item">
        <a class="tag-no-link">Water Policy</a>
      </li>
    <br>
    <a href="https://github.com/alex-truby/water-doc-db" class="project-link" target="_blank">View on GitHub</a>
  </div>
  <div class="project-card">
    <img src="/blog/images/alaska_ice2.jpg" alt="gee-water-image" class="project-image">
    <h3 class="project-title">gee-water</h3>
    <p>Python code to utilize Google Earth Engine (GEE) for water resoources earth observation projects.</p>
    <li class="tag-item">
        <a class="tag-no-link">Earth Observation</a>
    </li>
    <li class="tag-item">
        <a class="tag-no-link">Water</a>
      </li>
    <br>
    <a href="https://github.com/alex-truby/gee-water" class="project-link" target="_blank">View on GitHub</a>
  </div>

  <div class="project-card">
    <img src="/blog/images/sky_braid.jpg" alt="gee-water-image" class="project-image">
    <h3 class="project-title">monthly-electricity-predictions</h3>
    <p>A self contained model service & API for monthly electricity predictions using a sample dataset.</p>
    <li class="tag-item">
        <a class="tag-no-link">ML</a>
    </li>
    <li class="tag-item">
        <a class="tag-no-link">Software Engineering</a>
    </li>
    <li class="tag-item">
        <a class="tag-no-link">Energy</a>
    </li>
    <br>
    <a href="https://github.com/alex-truby/monthly-electricity-predictions" class="project-link" target="_blank">View on GitHub</a>
  </div>

  <div class="project-card">
    <img src="/blog/images/alaska_coast3.jpg" alt="gee-water-image" class="project-image-bottom">
    <h3 class="project-title">water-risk-solution-accelerator</h3>
    <p>Solutions accelerator accompanying notebooks highlighting streaming infrastructure I worked on while at Divirod.</p>
    <li class="tag-item">
        <a href="https://divirod.com" target="_blank" rel="noopener noreferrer" class="tag-link">Divirod</a>
    </li>
    <li class="tag-item">
        <a href="https://databricks.com" target="_blank" rel="noopener noreferrer" class="tag-link">Databricks</a>
    </li>
    <li class="tag-item">
        <a class="tag-no-link">Data Engineering</a>
    </li>
    <br>
    <a href="https://github.com/Divirod/water-risk-solution-accelerator" class="project-link" target="_blank">View on GitHub</a>
  </div>

  <div class="project-card">
    <img src="/blog/images/colorado_river.jpg" alt="gee-water-image" class="project-image">
    <h3 class="project-title">us-cancer-rates-esj</h3>
    <p>An evaluation of cancer rates at the US census tract level using environmental and demographic variables.</p>
    <li class="tag-item">
        <a class="tag-no-link">Statistics</a>
    </li>
    <li class="tag-item">
        <a class="tag-no-link">EJ</a>
    </li>
    <br>
    <a href="https://github.com/alex-truby/us_cancer_rates_environmental_impact" class="project-link" target="_blank">View on GitHub</a>
  </div>

</div>


