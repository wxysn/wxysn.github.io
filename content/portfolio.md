---
title: "Portfolio"
description: "Showcase of my projects and demos"
date: 2025-04-17
layout: "single"
type: "portfolio"
lang: "en"

# urls
aliases: ["/projects/"]
slug: "portfolio"

# No need to index this page
robots: "noindex, nofollow"

# Taxonomies
categories: ["Portfolio"]
---

_日本語版は[ここ](/ja/portfolio/)_

## 1. Door Placement Optimization Based on Flow Simulation

<div style="display: flex; gap: 8px; flex-wrap: wrap; align-items: center; margin-top: -1.5em;">
    <a href="https://github.com/WvXY/DoorPlacementOptimization" target="_blank" rel="noopener noreferrer">
        <img src="https://img.shields.io/badge/GitHub-Code-181717?style=for-the-badge&logo=github&logoColor=white" />
    </a>
    <span style="font-size: 1.2em;">|</span>
    <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
    <img src="https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=matplotlib&logoColor=white" />
    <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white" />
    <span style="font-size: 1.2em;">|</span>
    <img src="https://img.shields.io/badge/PCG-228B22?style=for-the-badge&logoColor=white" />
</div>

### Highlights

- Developed a door placement optimization program in **Python** for floor plan optimization
- Built a **2D navigation mesh (half-edge mesh, A\* pathfinding, funnel algorithm)** from scratch to simulate large-scale pedestrian flow
- Designed a runtime optimization system using **dynamic mesh split/merge operations** and **history tracking**
- Applied Data-Oriented Design (DOD) for high-speed processing

### Demo

<div style="display: flex; gap: 2px; flex-wrap: wrap;">
    <img src="/img/door_opti/case3.gif" width="355" alt="Case 1"/>
    <img src="/img/door_opti/case2.gif" width="355" alt="Case 2"/>
</div>

### Results

<img src="/img/door_opti/ress.svg"/>

### Challenges

{{< toggle title="Dynamic Mesh Processing" >}}

<strong>Relevant Code:</strong>  
<code>u_geometry.py</code>, <code>g_mesh.py</code>, <code>s_door_system.py</code>

<br>  
Implemented two basic operations on the half–edge structure:  
Splitting and **merging edges**.  
Maintaining the structure and preserving original mesh info during updates was critical.  
<br>

<strong>Use of Half–edge Structure:</strong>

<ul>
    <li>Embedded optimization-friendly info in each edge (e.g., face, opposite vertex).</li>
    <li>Assigned IDs to geometry for easier management and debug drawing.</li>
</ul>

<br>

<strong>History Functionality:</strong>

<ul>
    <li>Enabled retention of original edges through sequences of updates.</li>
    <li>Introduced history tracking to monitor geometry changes.</li>
    <li>History stored initial edge and position (0–1) to manage updates.</li>
</ul>

<br>  
<img src="/img/door_opti/dbg.gif" alt="Debug Draw"/>  
🔼 In debug mode, the door component dynamically moves clockwise along edges,
while the mesh is **split/merged**, yet the initial geometry is preserved.

{{< /toggle >}}

### Noteworthy Features

{{< toggle color="#15a8a1" title="Navigation Mesh Implementation" >}}

<strong>Relevant Code:</strong>  
<code>u_cdt.py</code>, <code>u_path_finding.py</code>, <code>g_navmesh.py</code>

<br>  
Implemented a custom navigation mesh from scratch to ensure flexibility.  
This involved mesh construction, A\* search, and the funnel algorithm—all with technical challenges.  
In particular, the funnel algorithm had many edge cases, making debugging difficult.  
<br>

<strong>Implementation Steps:</strong>

<ol>
    <li>
        <strong>2D Mesh Construction</strong><br>
        Used Python bindings for CDT (Constrained Delaunay Triangulation).<br>
        Converted resulting mesh into a half-edge structure and annotated edges with types and flags  
        to enable efficient subsequent optimization.
    </li>
    <li>
        <strong>A* Pathfinding</strong><br>
        Found shortest path through triangles (faces) on the mesh.
    </li>
    <li>
        <strong>Funnel Algorithm</strong><br>
        Used to calculate optimal movement path based on the triangle route.
    </li>
</ol>

{{< /toggle >}}

<!-- ============================= -->

{{< toggle color="#15a8a1" title="Runtime Optimization Algorithm" >}}
<strong>Relevant Code:</strong>  
<code>u*loader.py</code>, <code>s*\*\*\*.py</code>, <code>o_optimizer.py</code>, <code>f_layout.py</code>

<br>  
This program aims to optimize floor layouts considering flow lines by simulating human movement from sampling points.  
The main goal is to optimize door positions by minimizing the average travel distance as a loss function.  
<br>

<strong>Optimization Procedure:</strong>

<ol>
    <li>
        <strong>Load Initial Settings</strong><br>
        Door setup, room connection requirements, and optimization parameters are described in a TOML file and loaded.<br>
        The Flood Algorithm detects enclosed regions on the mesh and auto-generates room connectivity.
    </li>
    <li>
        <strong>Optimization Process</strong><br>
        Initial door positions are auto-generated based on connection rules.<br>
        Then, door positions are dynamically adjusted using the MCMC (Markov Chain Monte Carlo) algorithm.
    </li>
    <li>
        <strong>Finalize Optimal Configuration & Manage History</strong><br>
        Once optimal door positions are determined, the mesh data is updated to reflect the result.<br>
        Changes are tracked using the history management system to maintain optimal layouts.
    </li>
</ol>
{{< /toggle >}}

### Presentation Slides

<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vR1jLlie6EEiZ9U5lInwdKidgGKRUlAOo6SSXOjkihmi6e0dzDFSiiSa7Nsz8Mel1weD6SSquABEgQx/embed?start=false&loop=false&delayms=3000" frameborder="0" width="1280" height="440" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>

Slides for Master's Thesis Presentation (Revised)

### Libraries & References

- [PythonCDT (Constrained Delaunay Triangulation)](https://github.com/artem-ogre/PythonCDT)
- Funnel Algorithm: https://medium.com/@reza.teshnizi/the-funnel-algorithm-explained-visually-41e374172d2d

---

## 2. XenonVK: Vulkan Learning Engine

<div style="display: flex; gap: 8px; flex-wrap: wrap; align-items: center; margin-top: -1.5em;">
    <a href="https://github.com/WvXY/XenonVk" target="_blank" rel="noopener noreferrer">
        <img src="https://img.shields.io/badge/GitHub-Code-181717?style=for-the-badge&logo=github&logoColor=white" />    
    </a>
    <span style="font-size: 1.2em;">|</span>
    <img src="https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=cplusplus&logoColor=white" />
    <img src="https://img.shields.io/badge/Vulkan-EA1E32?style=for-the-badge&logo=vulkan&logoColor=white&logoWidth=80" />
    <img src="https://img.shields.io/badge/GLSL-3C6994?style=for-the-badge&logo=opengl&logoColor=white&logoWidth=80" />
    <img src="https://img.shields.io/badge/CMake-064F8C?style=for-the-badge&logo=cmake&logoColor=white" />
    <span style="font-size: 1.2em;">|</span>
    <img src="https://img.shields.io/badge/Game_Engine-8A2BE2?style=for-the-badge&logoColor=white" />
</div>

### Highlights

- Developed a C++ game engine to study Vulkan and engine architecture
- Implemented a 3D Vulkan renderer using **Blinn–Phong reflection model**
- Integrated CMake build system and GLSL shader compilation
- Added **OBJ mesh loading**, **game time system**, and **mouse/keyboard input**

### Challenges

{{< toggle color="#AA6C39" title="Learning Vulkan API and Game Engine Architecture" >}}

<strong>Topics:</strong> Vulkan API, game engine design, graphics programming

<br>

Vulkan is a low-level graphics API compared to OpenGL, requiring manual management of resources and synchronization.  
Initially, I referenced the “LittleVulkanEngine” video series to implement the basic pipeline and resource management framework.

<br>
<ul>
    <li>
    <strong>Issues:</strong>  
    Though I built a basic framework, the low-level complexity and code size overwhelmed me and slowed progress.
    </li>
    <li>
    <strong>Approach:</strong>  
    <ol>
        <li>Paused renderer development and focused on game engine architecture.</li>
        <li>Built a simpler 2D version to test primitives and basic physics animations.</li>
        <li>Studied OpenGL rendering pipelines via LearnOpenGL tutorials.</li>
        <li>Later implemented a tick-based time manager and ECS (Entity Component System) with help from ChatGPT, blogs, and books.</li>
    </ol>
    </li>
    <li>
    <strong>Results:</strong>  
    <ol>
        <li>Understood the internal engine flow and organized architecture through repeated refactoring inspired by existing engines.</li>
        <li>Resumed Vulkan implementation while handling validation layer warnings.</li>
        <li>Now progressing with render pass stabilization and debug features like wireframe rendering.</li>
    </ol>
  </li>
</ul>
{{< /toggle >}}

---

### Noteworthy Features

{{< toggle color="#15a8a1" title="CMake Build System & GitHub CI" >}}

<strong>Technologies:</strong> CMake, cross-platform development, GitHub Actions, Vulkan, GLSL

<br>

I use both Windows and macOS, so cross-platform compatibility was necessary.  
For this, I adopted **CMake** for its flexibility and extensibility.

<br>
<ol>
    <li>
<strong>CMake Build System:</strong>  
<ul>
    <li>Builds from the same codebase across Windows / Linux / macOS</li>
    <li>Integrated automatic GLSL shader compilation into CMake</li>
    <li>GLM, GLFW, and other libraries are auto-fetched and built through CMake</li>
</ul>
<br>
Special care was needed for Vulkan on macOS, requiring <strong>MoltenVK</strong> (Metal backend), which involved additional setup and debugging.
</li>
<li>
<strong>CI Integration:</strong>  
<ul>
    <li>Built auto-build workflows with GitHub Actions</li>
    <li>Builds triggered on push and pull requests</li>
    <li>Unit tests are not yet implemented but planned for the future</li>
</ul>
</li>
</ol>

These tools improve development reliability and reproducibility by design.

{{< /toggle >}}

<!-- --------------------------- -->

### Demo

<img src="/img/XenonVk/wireframe.gif" width="800" alt="WireRenderPass"/>
<div style="display: flex; gap: 20px; flex-wrap: wrap;">
    <img src="/img/XenonVk/wireframe3.png" width="350" alt="ワイヤーフレーム"/>
    <img src="/img/XenonVk/lge_latest.png" width="350" alt="複雑なシーン"/>
</div>

### References

- [Brendan Galea: LittleVulkanEngine](https://youtu.be/Y9U9IE0gVHA?si=42keJCaEPE-R697P)
- <https://gameprogrammingpatterns.com/>
- _Game Engine Architecture_ by Jason Gregory
- _Game Physics Engine Development_ by Ian Millington
- <https://learnopengl.com/>
- ChatGPT

---

## 3. Other Projects

### A\) [Apollonian Gasket Generator _(Rhinoceros/Python)_](https://github.com/WvXY/_TinyProjects/tree/master/ApollonianGasket)

<div style="display: flex; gap: 2px; flex-wrap: wrap;">
    <img src="/img/small/ap.gif" height="142"/>
    <img src="/img/small/1.jpg"  height="142"/>
    <img src="/img/small/2.jpg"  height="142"/>
    <img src="/img/small/3.png"  height="142"/>
    <img src="/img/small/6.png"  height="142"/>
</div>

### B\) [Interactive Voronoi Diagram_(Python/GLSL)_](https://github.com/WvXY/_toolkitPy/blob/main/demos/voronoi_interactive.py)

<div style="display: flex; gap: 12px; flex-wrap: wrap;">
    <img src="/img/small/voronoi1.gif"          height="200"/>
    <img src="/img/small/voronoi2che.gif"       height="200"/>
    <img src="/img/small/voronoi_shader.gif"    height="200"/>
</div>

### C\) [Publication: [PG24] Free-form Floor Plan Design](https://github.com/nobuyuki83/floor_plan)

<div style="display: flex; gap: 2px; flex-wrap: wrap;">
    <img src="/img/pg24/case1a.gif"   height="142"/>
    <img src="/img/pg24/case1b.gif"   height="142"/>
    <img src="/img/pg24/case1c.gif"   height="142"/>
    <img src="/img/pg24/case2.gif"    height="142"/>
    <img src="/img/pg24/case3.gif"    height="142"/>
</div>

<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vShKHsZw3p9qNFpXGKxKgCIxGIYGMbGtZOr7vMz6I29i2DjnqMHPeuCL3Sd-b6xPDxArpL6cOmm5Jds/embed?start=false&loop=false&delayms=3000" frameborder="0" width="1280" height="440" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>

---

This is the end of the portfolio. Thank you for your interest!

<!-- Thank you for reading! -->
