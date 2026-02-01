---
title: Welcome to Trilinos &ndash; Empowering Scientific Computing
keywords: homepage scientific libraries parallel computing
permalink: index.html
---

Trilinos is an advanced software framework designed to facilitate the development of high-performance scientific applications. Trilinos provides a comprehensive suite of libraries and tools that support a wide range of computational tasks, from linear algebra and optimization to differential equations and mesh generation.

With a focus on scalability and efficiency, Trilinos enables researchers and engineers to tackle complex problems across various fields, including engineering, physics, and applied mathematics. Our modular architecture allows users to customize and extend functionalities, ensuring that Trilinos meets the evolving needs of the scientific community.

Join us in harnessing the power of Trilinos to drive innovation and discovery in computational science!

---

## Quick Links

Explore Trilinos resources:

<div class="quick-links-grid">
    <div class="quick-link-box">
    <h3><a href="getting_started.html">Getting started</a></h3>
    <p>First steps with Trilinos: installation and usage</p>
  </div>
  <div class="quick-link-box">
    <h3><a href="events.html">Events</a></h3>
    <p>Stay updated on workshops, webinars, and community events.</p>
  </div>
  <div class="quick-link-box">
    <h3><a href="https://github.com/trilinos/Trilinos">Trilinos GitHub Repository</a></h3>
    <p>Access the source code and contribute to Trilinos development.</p>
  </div>
  <div class="quick-link-box">
    <h3><a href="packages-by-area.html">Doxygen Documentation</a></h3>
    <p>Explore the API documentation for Trilinos packages.</p>
  </div>
</div>

---

## Capabilities

Trilinos offers a robust framework for scientific computing, providing tools and libraries designed to solve complex engineering and scientific problems. Explore our [capabilities](capabilities.html):

<div class="capabilities-grid">
{% for capabilityArea in site.capabilityAreas %}
<div class="capability-box">
<h3><a href="capabilities.html#{{ capabilityArea.label }}">{{ capabilityArea.name }}</a></h3>
{{ capabilityArea.content }}
</div>
{% endfor %}
</div>
