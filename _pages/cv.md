---
layout: archive
title: "CV"
permalink: /cv/
author_profile: true
redirect_from:
  - /resume
---

{% include base_path %}

Education
======
* Ph.D in Computer Science, Louisiana State University, Baton Rouge, USA, 2021-2026 (expected)
* B.S. in Information and Computation Science(Math), Northeastern University, Shenyang, CN, 2016-2020

Work experience
======
* May 2025 - present: Machine Learning Engineer
  * Louisiana State University
  * Designed a LLM multi-agent framework for athlete injury analysis, rehabitation, and coversation interface with users (coach, athletes) 
  * Supervisor: Dr.Mingxuan Sun, Nicholas P Totaro
* Aug 2021 - present: Research Assistant
  * Louisiana State University
  * Designed a spatiotemporal fault-injection framework (STAFI) for ADAS, integrating Progressive Metric-guided Bit Search
  and context-aware timing to reveal safety-critical vulnerabilities in OpenPilot–CARLA closed-loop driving simulations.
  * Built multi-level text-aligned time-series forecasting models that decompose signals into trend/seasonal/residual components and align them with interpretable language anchors to enhance LLM reasoning and forecasting accuracy.
  * Proposed a practical backdoor attack that swaps in a malicious attention head, achieving high attack success with minimal
  clean-accuracy impact and strong resilience to modern defenses.
  * Supervisor: Dr.Mingxuan Sun

* Summer 2021: Research Assistant
  * Northeastern University
  * Implemented and optimized semantic segmentation models for industrial predictive-maintenance applications in
  collaboration with Ansteel Group.
  * Reduced system downtime by 30% through image-based defect detection and automated data labeling pipelines.
  * Supervisor: Dr.Zhuofu Deng
  
Skills
======
* Language: Python, C++, Java, MATLAB
* Machine learning: pytorch, tensorflow, Huggingface, Scikit-learn, ONNX Runtime, OpenCV
* Tools: Numpy, Pandas, Docker, AWS, Git, Jupyter, Linux

Publications
======
  <ul>{% for post in site.publications reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
Talks
======
  <ul>{% for post in site.talks reversed %}
    {% include archive-single-talk-cv.html  %}
  {% endfor %}</ul>
  
experience
======
  <ul>{% for post in site.experience reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>
  
Service
======
  <ul>{% for post in site.service reversed %}
    {% include archive-single-cv.html %}
  {% endfor %}</ul>

<div class="cv-download-links">
  <a href="{{ base_path }}/files/cv.pdf" class="btn btn--primary">Download CV as PDF</a>
</div>