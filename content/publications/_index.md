---
title: "Publications"
description: "Publications that I have written or contributed to in my current and previous roles."
# 1. To ensure Netlify triggers a build on our exampleSite instance, we need to change a file in the exampleSite directory.
theme_version: '2.8.2'
layout: about_me
cascade:
  featured_image: "/images/japanese_moon.jpg"
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

  /* Moves image up (20% from top) */
  .project-image-custom {
        width: 100%;
        height: 150px;
        object-fit: cover;
        border-radius: 8px;
        object-position: 50% 80%; 
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
    <img src="/blog/images/london.jpg" alt="gee-water-image" class="project-image-bottom">
    <h5>December 2024</h5>
    <h3 class="project-title">Evaluating the Water Level Gage Network Density of New York City</h3>
    <p>A white paper on water gage depolyment density in NYC.</p>
    <li class="tag-item">
        <a href="https://divirod.com" target="_blank" rel="noopener noreferrer" class="tag-link">Divirod</a>
    </li>
    <li class="tag-item">
        <a class="tag-no-link">Water Resources</a>
    </li>
    <li class="tag-item">
        <a class="tag-no-link">EJ</a>
    </li>
    <br>
    <a href="https://www.linkedin.com/pulse/evaluating-water-level-gage-network-density-new-york-city-divirod-suvtc/?trackingId=0vzP%2Btn2TV2IOnCkRHT6ew%3D%3D" class="project-link" target="_blank">Read the article</a>
  </div>

  <div class="project-card">
    <img src="/blog/images/alaska_coast2.jpg" alt="gee-water-image" class="project-image-bottom">
    <h5>July 2024</h5>
    <h3 class="project-title">Unlocking True Water Risk Assessment Worldwide</h3>
    <p>Solutions accelerator blog  outlining the impact of Divirod's work to harness big data for water resources issues.</p>
    <li class="tag-item">
        <a href="https://divirod.com" target="_blank" rel="noopener noreferrer" class="tag-link">Divirod</a>
    </li>
    <li class="tag-item">
        <a href="https://databricks.com" target="_blank" rel="noopener noreferrer" class="tag-link">Databricks</a>
    </li>
    <li class="tag-item">
        <a class="tag-no-link">Water Resources</a>
    </li>
    <br>
    <a href="https://www.databricks.com/blog/unlocking-true-water-risk-assessment-worldwide" class="project-link" target="_blank">Read the article</a>
  </div>

  <div class="project-card">
    <img src="/blog/images/alaska_coast3.jpg" alt="gee-water-image" class="project-image-bottom">
    <h5>July 2024</h5>
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
    <a href="https://github.com/Divirod/water-risk-solution-accelerator" class="project-link" target="_blank">See the code base</a>
  </div>

  <div class="project-card">
    <img src="/blog/images/cv_sunset.jpg" alt="gee-water-image" class="project-image-bottom">
    <h5>August 2023</h5>
    <h3 class="project-title">Supporting a rapid, just and equitable transition away from coal</h3>
    <p>Written by Carbon Trust, utilizing anlysis from my time at TransitionZero. </p>
    <li class="tag-item">
        <a href="https://transitionzero.org" target="_blank" rel="noopener noreferrer" class="tag-link">TransitionZero</a>
    </li>
    <li class="tag-item">
        <a class="tag-no-link">Energy Transition</a>
    </li>
    <br>
    <a href="https://ctprodstorageaccountp.blob.core.windows.net/prod-drupal-files/2023-10/Supporting%20a%20rapid%20just%20and%20equitable%20transition%20away%20from%20coal.pdf" class="project-link" target="_blank">Read the report</a>
  </div>

  <div class="project-card">
    <img src="/blog/images/fall_temple_roof.jpg" alt="gee-water-image" class="project-image">
    <h5>August 2023</h5>
    <h3 class="project-title">C3PI Methodology Document</h3>
    <p>Technical document outlining TransitionZero's Coal to Clean Price Index (C3PI). </p>
    <li class="tag-item">
        <a href="https://transitionzero.org" target="_blank" rel="noopener noreferrer" class="tag-link">TransitionZero</a>
    </li>
    <li class="tag-item">
        <a class="tag-no-link">Energy Transition</a>
    </li>
    <li class="tag-item">
        <a class="tag-no-link">Energy Economics</a>
    </li>
    <br>
    <a href="https://ctprodstorageaccountp.blob.core.windows.net/prod-drupal-files/2023-10/Supporting%20a%20rapid%20just%20and%20equitable%20transition%20away%20from%20coal.pdf" class="project-link" target="_blank">Read the report</a>
  </div>

  <div class="project-card">
    <img src="/blog/images/river.jpg" alt="gee-water-image" class="project-image-bottom">
    <h5>April 2021</h5>
    <h3 class="project-title">Turning the Supertanker (Full Report)</h3>
    <p>Aided in the underlying analysis for this report.</p>
    <li class="tag-item">
        <a href="https://transitionzero.org" target="_blank" rel="noopener noreferrer" class="tag-link">TransitionZero</a>
    </li>
    <li class="tag-item">
        <a class="tag-no-link">Energy Transition</a>
    </li>
    <br>
    <a href="https://www.transitionzero.org/insights/turning-the-supertanker" class="project-link" target="_blank">Read the report</a>
  </div>

  <div class="project-card">
    <img src="/blog/images/japanese_boat.jpg" alt="gee-water-image" class="project-image-custom">
    <h5>April 2021</h5>
    <h3 class="project-title">Turning the Supertanker (Interactive Report)</h3>
    <p>My first ever front end endevour! An interactive report to accompany TransitionZero's Turning the Supertanker Report. </p>
    <li class="tag-item">
        <a href="https://transitionzero.org" target="_blank" rel="noopener noreferrer" class="tag-link">TransitionZero</a>
    </li>
    <li class="tag-item">
        <a class="tag-no-link">Energy Transition</a>
    </li>
    <br>
    <a href="https://turning-the-supertanker.transitionzero.org/" class="project-link" target="_blank">Read the interactive report</a>
  </div>

</div>


