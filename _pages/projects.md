---
enabled: true
layout: page
permalink: /projects/
title: Research Projects
description: This page serves to display notable projects I have had the privilege to work on throughout my professional career.
nav: true
nav_order: 2
#display_categories: [Research, Educational]
horizontal: false
---
**Category Prediction in OGBN-Products Dataset** —  *PyTorch Geometric, Graph Convolutional Networks*
Implemented a graph convolutional network (GCN) to predict the category of a product in Amazon’s product co-purchasing 
network. Trained on a subgraph with 100,000 nodes and achieved an accuracy of 91%.

**REINFORCE Algorithm for Continuous Cart Pole Environment** —  *Reinforcement Learning, Gym, PyTorch*
Deployed the REINFORCE algorithm with target and policy networks such that the agent learned to strategically
accelerate and reach a goal state on a continuous sinusoidal hill. The agent solved the task every five attempts.

**Deep Q-Learning for Frozen Lake Environment** —  *Reinforcement Learning, Gym, PyTorch*
Trained an agent to reach the goal state in the maximal, 8x8 slippery (stochastic) environment using deep Q-learning.
The agent learned to complete the task with 100% accuracy after approximately 200 iterations.

**Generative Adversarial Network for Face Generation** —  *Generative Adversarial Networks, PyTorch*
Developed a generative adversarial network (GAN) that generated new faces after training on a dataset of characters
from *The Simpsons*.

**Autoencoders for CIFAR10 Recoloring** —  *Autoencoders, U-Nets, Convolutional Neural Networks, PyTorch*
Implemented an autoencoder and U-net that recolored grayscale-converted images from the CIFAR10 dataset. Minimized 
average loss to approximately 0.01.

**Multi-Modal Digital Assistant** —  *Computer Vision, Natural Language Processing, JavaFX*
Collaborated with 5 teammates to create a multi-modal digital assistant that launched the GUI and addressed the
user upon face detection and recognition. Implemented the program’s response to text inputs through CFG, CYK,
NER, LSTM, and BERT. Extended the application with Google and OpenAI API, and increased usability with hand
gesture commands.

**3D Bounded Knapsack Problem with Polyominoes** —  *Knapsack Optimization, Genetic Algorithm, JavaFX*
Coordinated with 6 teammates to develop a recursive algorithm that provided exact cover solutions to a 2D grid,
given the dimensions and available pieces as input. Adapted the program to solve knapsack problems in a bounded
3D space visualized with JavaFX. Extended the application to a Pentris game and trained a bot that outperformed
human players using genetic algorithms.

[//]: #

<!-- pages/projects.md -->
<div class="projects">
{%- if site.enable_project_categories and page.display_categories %}
  <!-- Display categorized projects -->
  {%- for category in page.display_categories %}
  <h2 class="category">{{ category }}</h2>
  {%- assign categorized_projects = site.projects | where: "category", category -%}
  {%- assign sorted_projects = categorized_projects | sort: "importance" %}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
    {% if project.visible %}
      {% include projects_horizontal.html %}
    {% endif %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
    {% if project.visible %}
      {% include projects.html %}
    {% endif %}
    {%- endfor %}
  </div>
  {%- endif -%}
  {% endfor %}

{%- else -%}
<!-- Display projects without categories -->
  {%- assign sorted_projects = site.projects | sort: "importance" -%}
  <!-- Generate cards for each project -->
  {% if page.horizontal -%}
  <div class="container">
    <div class="row row-cols-2">
    {%- for project in sorted_projects -%}
    {% if project.visible %}
      {% include projects_horizontal.html %}
    {% endif %}
    {%- endfor %}
    </div>
  </div>
  {%- else -%}
  <div class="grid">
    {%- for project in sorted_projects -%}
    {% if project.visible %}
      {% include projects.html %}
    {% endif %}
    {%- endfor %}
  </div>
  {%- endif -%}
{%- endif -%}
</div>
