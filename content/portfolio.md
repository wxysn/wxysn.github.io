---
title: "Portfolio"
description: "Showcasing my projects."
date: 2025-03-04
layout: "single"
type: "portfolio"

# urls 
aliases: ["/projects/"]
# url: "/portfolio/"
slug: "portfolio"

# No need to index this page
robots: "noindex, nofollow"

# Taxonomies
categories: ["Portfolio"]
---

## 1. XenonVk::Vulkan Game Engine

    Skills： C++, Vulkan, GLSL, System Design, CMake

<!-- 　ゲームエンジンの仕組みを理解するために、Vulkanを使って3Dゲームエンジンを作成しています。最初はBrendan GaleaのYouTube動画に沿って大まかな枠を作成しました。現在は主に派生した2Dゲームエンジンで理解を深めながら機能を追加しています。ここで、3Dでも動かすようにテンプレートやシステム設計に工夫を入れています。今後はこのプロジェクトに追加する予定です。 -->

This is a vulkan game engine for personal study and interests. It is implemented in C++ and Vulkan. 

- Code: [https://github.com/WvXY/XenonVk](https://github.com/WvXY/XenonVk)

<img src="/assets/img/XenonVk/lge_demo.gif" width="450"/>
<img src="/assets/img/XenonVk/lge_latest.png" width="450"/>

<img src="/assets/img/XenonVk/wireframe1.png" width="300"/>
<img src="/assets/img/XenonVk/wireframe2.png" width="300"/>
<img src="/assets/img/XenonVk/wireframe3.png" width="300"/>

_The demo gif is compressed and the color is actually continuous and better._

##### Physics in 2D(WIP)

<img src="/assets/img/XenonVk/xev2phy.gif" width="300"/>

#### Structure

Currently, the engine is structured as follows:

<img src="/assets/img/XenonVk/XenonVK_structure.png" width=500>

#### Status

| Feature                       | Description                                              | Status |
| ----------------------------- | -------------------------------------------------------- | ------ |
| Vulkan Renderer               | Implemented a basic Vulkan renderer for 3D rendering.    | ✅ Done |
| OBJ Model Loading             | Integrated functionality for loading OBJ models.         | ✅ Done |
| Camera Control                | Developed mouse and keyboard-based camera movement.      | ✅ Done |
| Keyboard Input                | Implemented responsive keyboard input handling.          | ✅ Done |
| Time Control                  | Added real-time time control for simulations.            | ✅ Done |
| Texture Mapping               | Implementing texture mapping for 3D objects.             | ⏳ WIP  |
| Shadow Mapping                | Plan to incorporate shadow mapping for dynamic lighting. | 📝 TODO |
| Physics Engine                | Ongoing development of a custom physics engine.          | 🔨 WIP  |
| UI                            | Planning to integrate UI support using ImGui.            | 📝 TODO |
| Entity Component System (ECS) | Designing an ECS architecture to handle game objects.    | 📝 TODO |

#### Reference

- [Brendan Galea: LittleVulkanEngine](https://youtu.be/Y9U9IE0gVHA?si=42keJCaEPE-R697P)
- <https://gameprogrammingpatterns.com/>
- Game Engine Architecture by Jason Gregory
- Game Physics Engine Development by Ian Millington
- <https://learnopengl.com/>

---

## 2. WvXY_ToolboxPy::Voronoi Diagram Experiment

    Skills： Python, PyTorch, ModernGL, GLSL

<!-- 私の修士研究では陰的表現で自由な間取り構成を目標としています。そのため、ボロノイ図を用いて自由な形の生成方法と制御方法について実験します。

- 重み付けボロノイ図（パワーダイアグラム、power diagram）をインタラクティブに生成するための実験ツールです。
- 点を追加し、複数の母点(site)をグループ化し、Lloyd法によるリラクゼーションを行います。
- シェーダーを用いてボロノイ図を描画する機能を追加しました。
- GPUによる高速計算を目指すため、PyTorchとModernGLを使用しています。 -->

Part of my research experiment using my personal toolbox.

Voronoi relaxation is computed using the Lloyd's algorithm. You can add points by left clicking on the canvas and press Z for Voronoi relaxation. Also, when clicking right, there will be more sites and will be grouped to existing sites to create more variety(my experiment).

The distance metric is Minkowski distance in general. The Minkowski distance at point $$P$$ and $$Q$$ is defined as:

$$D(P, Q) = \left(\sum_{i=1}^{N} |p_i - q_i|^p\right)^{\frac{1}{p}}$$

When $$p$$ is 1, it is Manhattan distance, when $$p$$ is 2, it is Euclidean distance, and when $$p$$ is $$\infty$$, it is equivalent to Chebyshev distance.

- Code: [WvXY_ToolboxPy::voronoi_interactive.py](https://github.com/WvXY/WvXY_ToolboxPy/blob/main/demos/voronoi_interactive.py), 
[WvXY_ToolboxPy::voronoi_system.py](https://github.com/WvXY/WvXY_ToolboxPy/blob/main/w_tbx/Renderer/voronoi_system.py)

<img src="/assets/img/demos/voronoi1.gif" width="300" height="300"/>
<img src="/assets/img/demos/voronoi2che.gif" width="300" height="300"/>
<img src="/assets/img/demos/voronoi_shader.gif" width="300" height="300"/>

#### Reference

- [https://en.wikipedia.org/wiki/Voronoi_diagram](https://en.wikipedia.org/wiki/Voronoi_diagram)
- F. AURENHAMMER, POWER DIAGRAMS: PROPERTIES, ALGORITHMS AND APPLICATIONS, 1987

----

## 3. Mass-Spring System For Procedural Dungeon Generation

    Skills: Python, Numpy, ModernGL, Matplotlib


<!-- - 質点-バネモデルを用いて、エネルギーを最小化することで、異なる部屋を接続します。
- Matplotlibを用いて可視化しましたが、描画が遅いのでModernGLを使って描画することに切り替えました。 -->

- Use mass-spring model to connect different rooms by minimizing the energy.
- The demo is for procedural dungeon generation. The rooms are connected by mass-spring model and the connections are rebuilt when reaching equilibrium.

- Code: [WvXY_ToolboxPy::mass_spring_model_plt.py](https://github.com/WvXY/WvXY_ToolboxPy/blob/main/demos/mass_spring_model_plt.py), 
  [WvXY_ToolboxPy::mass_spring_model.py](https://github.com/WvXY/WvXY_ToolboxPy/blob/main/demos/mass_spring_model.py)

<img src="/assets/img/demos/spring_model1.gif" width="325" height=250/>
<img src="/assets/img/demos/spring_model2.gif" width="325" height=250/>
<img src="/assets/img/demos/mssGL.gif" width="250"/>

#### Reference

- [nobuyuki83/Physics-based_Animation_2023S](https://github.com/nobuyuki83/Physics-based_Animation_2023S)
- [https://www.gamedeveloper.com/programming/procedural-dungeon-generation-algorithm](https://www.gamedeveloper.com/programming/procedural-dungeon-generation-algorithm)

-----

## 4. Geometries:: Apollonian Gasket & Nurbs Spline

    Skills: Python, Grasshopper(Rhino), Math

### Apollonian Gasket

A script for grasshopper.

<!-- Apollonian gasketを作るには、既知の3つの円の曲率と中心を使って、デカルトの定理により新しい円の曲率を計算します。そして、複素数を用いて新しい円の中心を求めます。この手順を繰り返して無限に続く円のパターンを作成します。 -->

- Code: [WvXY-Utils::ApollonianGasket](https://github.com/WvXY/WvXY-Utils/tree/master/demos/ApollonianGasket)

<img src="/assets/img/demos/ap.gif" height="300"/>
<img src="/assets/img/demos/1.jpg" height="300"/>
<img src="/assets/img/demos/2.jpg" height="300"/>
<img src="/assets/img/demos/3.png" height="300"/>
<img src="/assets/img/demos/4.png" height="300"/>
<img src="/assets/img/demos/6.png" height="300"/>

### Nurbs Spline

- Code: [WvXY_ToolboxPy::nurbs.py](https://github.com/WvXY/WvXY_ToolboxPy/blob/main/w_tbx/Geometry/nurbs.py)

<img src="/assets/img/demos/butterfly.svg" width="900"/>

_The butterfly is created by Nurbs Spline._

#### Reference

- [https://arxiv.org/pdf/math/0101066v1.pdf](https://arxiv.org/pdf/math/0101066v1.pdf)
- [https://en.wikipedia.org/wiki/Apollonian_gasket](https://en.wikipedia.org/wiki/Apollonian_gasket)
- https://en.wikipedia.org/wiki/Non-uniform_rational_B-spline
- Hu, Y., Jiang, X., Huo, G. et al. A novel method for calculating interpolation points of NURBS curves based on chord length-parameter ratio. Int J Adv Manuf Technol 129, 2843–2860 (2023). https://doi.org/10.1007/s00170-023-12427-5


-----

## Other Work: Design Portfolio

    Skills: Photoshop, Illustrator, InDesign, AutoCAD, SketchUp, Rhino, V-ray, lumion

<!-- 学部時代で建築設計の授業を受けていました。建築設計の基本的な考え方、デザインのプロセス、建築物の構造、環境設計などを学びました。以下のリンクからポートフォリオを読むことができます。 -->

I have taken architectural design courses during my undergraduate studies. I learned the basic concepts of architectural design, the design process, building structures, and environmental design. You access it from the link below.

- Dropbox link: [Architecture Portfolio(Last update: 2023-06)](https://www.dropbox.com/scl/fi/i9haf5bx9ymkkia6u61zm/Academic_Portfolio_WuXuanyu.pdf?rlkey=4sdhgc5byhpnddx2r1lfnetcn&dl=0)

--------------
<!-- _以上になります。ご覧いただきありがとうございます!!_ -->
Thank you for reading!
