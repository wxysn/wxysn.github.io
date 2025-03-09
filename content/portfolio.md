---
title: "Portfolio"
description: "Showcasing my projects."
date: 2025-03-09
layout: "single"
type: "portfolio"

# urls
aliases: ["/projects/"]
slug: "portfolio"

# No need to index this page
robots: "noindex, nofollow"

# Taxonomies
categories: ["Portfolio"]
---

<!-- <h2 style="margin-bottom: 0px;">1. Door Placement Optimization based on Human Traffic Simulation</h2> -->

## 1. Door Placement Optimization based on Human Traffic Simulation

<div style="display: flex; gap: 8px; flex-wrap: wrap; align-items: center; margin-top: -1.5em;">
    <a href="https://github.com/WvXY/DoorPlacementOptimization" target="_blank" rel="noopener noreferrer">
        <img src="https://img.shields.io/badge/GitHub-Source%20Code-181717?style=for-the-badge&logo=github&logoColor=white" />
    </a>
    <span style="font-size: 1.2em;">|</span>
    <img src="https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white" />
    <img src="https://img.shields.io/badge/Matplotlib-11557C?style=for-the-badge&logo=matplotlib&logoColor=white" />
    <img src="https://img.shields.io/badge/NumPy-013243?style=for-the-badge&logo=numpy&logoColor=white" />
    <span style="font-size: 1.2em;">|</span>
    <img src="https://img.shields.io/badge/PCG-228B22?style=for-the-badge&logoColor=white" />
</div>

### Highlights

- Developed a *Python* program to optimize door placement for optimizing floor plan design.
- Implemented a _2D navigation mesh(half-edge mesh, A\* pathfinding, funnel algorithm)_ from scratch for large-scale human traffic simulation.
- Designed a runtime optimization system with _dynamic mesh cut/merge operations_ and _history tracking_.
- Applied data-oriented design(DOD) for better performance.

<!-- ### Description

- Problem: In architectural design, door placement significantly impacts movement flow and overall building efficiency.
- Solution: Optimized door placement through human traffic simulation to enhance spatial efficiency. -->
### Demo

<div style="display: flex; gap: 2px; flex-wrap: wrap;">
    <img src="/img/door_opti/case3.gif" width="355" alt="Case1"/>
    <img src="/img/door_opti/case2.gif" width="355" alt="Case2"/>
</div>

### Results
<img src="/img/door_opti/ress.svg"/>

### Presentation Slides

<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vR1jLlie6EEiZ9U5lInwdKidgGKRUlAOo6SSXOjkihmi6e0dzDFSiiSa7Nsz8Mel1weD6SSquABEgQx/embed?start=false&loop=false&delayms=3000" frameborder="0" width="1280" height="440" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>

_My presentation slide for master thesis defence in UTokyo.(Modified)_

### Dependencies \& References

- [PythonCDT (Constrained Delaunay Triangulation)](https://github.com/artem-ogre/PythonCDT)
- Funnel Algorithm: https://medium.com/@reza.teshnizi/the-funnel-algorithm-explained-visually-41e374172d2d

---

## 2. XenonVK::Vulkan Engine for Learning

<div style="display: flex; gap: 8px; flex-wrap: wrap; align-items: center; margin-top: -1.5em;">
    <!-- GitHub Badge -->
    <a href="https://github.com/WvXY/XenonVk" target="_blank" rel="noopener noreferrer">
        <img src="https://img.shields.io/badge/GitHub-Source%20Code-181717?style=for-the-badge&logo=github&logoColor=white" />    
    </a>
    <span style="font-size: 1.2em;">|</span>
    <!-- Techs (C++, Vulkan, GLSL, CMake) -->
    <img src="https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=cplusplus&logoColor=white" />
    <img src="https://img.shields.io/badge/Vulkan-EA1E32?style=for-the-badge&logo=vulkan&logoColor=white&logoWidth=80" />
    <img src="https://img.shields.io/badge/GLSL-3C6994?style=for-the-badge&logo=opengl&logoColor=white&logoWidth=80" />
    <img src="https://img.shields.io/badge/CMake-064F8C?style=for-the-badge&logo=cmake&logoColor=white" />
    <span style="font-size: 1.2em;">|</span>
    <!-- Category -->
    <img src="https://img.shields.io/badge/Rendering-8A2BE2?style=for-the-badge&logoColor=white" />
</div>

### Highlights

- Developing a game engine in C++ to explore Vulkan and engine/rendering techniques.
- Implemented a 3D Vulkan renderer with the _Blinn–Phong reflection model_.
- Integrated a CMake build system and GLSL shader compilation.
- Added support for _OBJ mesh loading_, a _game time system_, and _mouse/keyboard input_.

<img src="/img/XenonVk/lge_demo.gif" width="800" alt="Simple demo"/>

<div style="display: flex; gap: 20px; flex-wrap: wrap;">
    <img src="/img/XenonVk/wireframe3.png" width="350" alt="Wireframe"/>
    <img src="/img/XenonVk/lge_latest.png" width="350" alt="Complex scene"/>
</div>

### Reference

- [Brendan Galea: LittleVulkanEngine](https://youtu.be/Y9U9IE0gVHA?si=42keJCaEPE-R697P)
- <https://gameprogrammingpatterns.com/>
- _Game Engine Architecture_ by Jason Gregory
- _Game Physics Engine Development_ by Ian Millington
- <https://learnopengl.com/>

----

## 3. Gallery of Other Projects
### A\) [Apollonian Gasket Generator *(Rhinoceros/Python)*](https://github.com/WvXY/_TinyProjects/tree/master/ApollonianGasket)

<div style="display: flex; gap: 2px; flex-wrap: wrap;">
    <img src="/img/small/ap.gif" height="142"/>
    <img src="/img/small/1.jpg"  height="142"/>
    <img src="/img/small/2.jpg"  height="142"/>
    <img src="/img/small/3.png"  height="142"/>
    <img src="/img/small/6.png"  height="142"/>
</div>


### B\) [Voronoi Diagram Experiments *(Python/GLSL)*](https://github.com/WvXY/_toolkitPy/blob/main/demos/voronoi_interactive.py)

<div style="display: flex; gap: 12px; flex-wrap: wrap;">
    <img src="/img/small/voronoi1.gif"          height="200"/>
    <img src="/img/small/voronoi2che.gif"       height="200"/>
    <img src="/img/small/voronoi_shader.gif"    height="200"/>
</div>

### C\) [ [PG24] Free-form Floor Plan Design *(Rust)*](https://github.com/nobuyuki83/floor_plan)

<div style="display: flex; gap: 2px; flex-wrap: wrap;">
    <img src="/img/pg24/case1a.gif"   height="142"/>
    <img src="/img/pg24/case1b.gif"   height="142"/>
    <img src="/img/pg24/case1c.gif"   height="142"/>
    <img src="/img/pg24/case2.gif"    height="142"/>
    <img src="/img/pg24/case3.gif"    height="142"/>
</div>

<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vShKHsZw3p9qNFpXGKxKgCIxGIYGMbGtZOr7vMz6I29i2DjnqMHPeuCL3Sd-b6xPDxArpL6cOmm5Jds/embed?start=false&loop=false&delayms=3000" frameborder="0" width="1280" height="440" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>

<!-- ### C\) Archictural Design *(AutoCAD/SketchUp/Rhinoceros/InDesign/Illustrator)*

- Dropbox link: [Architecture Portfolio(Last update: 2023-06)](https://www.dropbox.com/scl/fi/i9haf5bx9ymkkia6u61zm/Academic_Portfolio_WuXuanyu.pdf?rlkey=4sdhgc5byhpnddx2r1lfnetcn&dl=0) -->

<!-- ## Other Work: Design Portfolio

    Skills: Photoshop, Illustrator, InDesign, AutoCAD, SketchUp, Rhino, V-ray, lumion

<!-- 学部時代で建築設計の授業を受けていました。建築設計の基本的な考え方、デザインのプロセス、建築物の構造、環境設計などを学びました。以下のリンクからポートフォリオを読むことができます。 -->

<!-- I have taken architectural design courses during my undergraduate studies. I learned the basic concepts of architectural design, the design process, building structures, and environmental design.  -->



---

<!-- _以上になります。ご覧いただきありがとうございます!!_ -->

Thank you for reading!
