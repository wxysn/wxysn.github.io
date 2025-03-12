---
title: "ポートフォリオ[WIP]"
description: "個人のプロジェクトの紹介と成果物のデモ"
date: 2025-03-10
layout: "single"
type: "portfolio"
lang: "jp"

# urls
aliases: ["/projects/"]
slug: "portfolio"

# No need to index this page
robots: "noindex, nofollow"

# Taxonomies
categories: ["Portfolio"]
---
## 1. 動線シミュレーションに基づくドア配置最適化

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

### ハイライト

- **Python** を用いて、間取り設計の最適化のためのドア配置最適化プログラムを開発
- 大規模な人の流れシミュレーションのために、**2Dナビゲーションメッシュ（半エッジメッシュ、A\*経路探索、ファンネルアルゴリズム）** をゼロから実装
- **動的メッシュの切断/統合操作** と **履歴追跡** を活用したランタイム最適化システムを設計
- 高速処理のためにデータ指向設計(DOD)を適用

### Demo

<div style="display: flex; gap: 2px; flex-wrap: wrap;">
    <img src="/img/door_opti/case3.gif" width="355" alt="ケース1"/>
    <img src="/img/door_opti/case2.gif" width="355" alt="ケース2"/>
</div>

### 結果
<img src="/img/door_opti/ress.svg"/>

### 苦労した箇所
#### 1．**ナビゲーションメッシュの実装**：

関連コード

<!-- ナビゲーションメッシュの実装は、半エッジメッシュの構築、A\*経路探索、ファンネルアルゴリズムの実装など、多くの技術的課題があった。特に、ファンネルアルゴリズムの実装は、複雑なエッジケースが多く、デバッグが難しかった。 -->

#### 2. **ランタイムでのメッシュ最適化システム**：
<!-- ランタイム最適化システムの設計は、メッシュの切断/統合操作の実装、履歴追跡の設計、データ指向設計の適用など、多くの技術的課題があった。特に、データ指向設計の適用は、プログラムの複雑さを増すことがあるため、慎重に設計する必要があった。 -->

### 注目してほしい箇所
1. **ECSシステム**：
<!-- ナビゲーションメッシュの実装は、Half-edge Meshの構築、A\*経路探索、ファンネルアルゴリズムの実装など、多くの技術的課題があった。特に、ファンネルアルゴリズムの実装は、複雑なエッジケースが多く、デバッグが難しかった。 -->


### プレゼンテーションスライド

<iframe src="https://docs.google.com/presentation/d/e/2PACX-1vR1jLlie6EEiZ9U5lInwdKidgGKRUlAOo6SSXOjkihmi6e0dzDFSiiSa7Nsz8Mel1weD6SSquABEgQx/embed?start=false&loop=false&delayms=3000" frameborder="0" width="1280" height="440" allowfullscreen="true" mozallowfullscreen="true" webkitallowfullscreen="true"></iframe>

修士論文発表用スライド（修正版）

### ライブラリ & 参考文献

- [PythonCDT (制約付きドロネー三角形分割)](https://github.com/artem-ogre/PythonCDT)
- ファンネルアルゴリズム: https://medium.com/@reza.teshnizi/the-funnel-algorithm-explained-visually-41e374172d2d

---

## 2. XenonVK::学習用Vulkanエンジン

<div style="display: flex; gap: 8px; flex-wrap: wrap; align-items: center; margin-top: -1.5em;">
    <a href="https://github.com/WvXY/XenonVk" target="_blank" rel="noopener noreferrer">
        <img src="https://img.shields.io/badge/GitHub-Source%20Code-181717?style=for-the-badge&logo=github&logoColor=white" />    
    </a>
    <span style="font-size: 1.2em;">|</span>
    <img src="https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=cplusplus&logoColor=white" />
    <img src="https://img.shields.io/badge/Vulkan-EA1E32?style=for-the-badge&logo=vulkan&logoColor=white&logoWidth=80" />
    <img src="https://img.shields.io/badge/GLSL-3C6994?style=for-the-badge&logo=opengl&logoColor=white&logoWidth=80" />
    <img src="https://img.shields.io/badge/CMake-064F8C?style=for-the-badge&logo=cmake&logoColor=white" />
    <span style="font-size: 1.2em;">|</span>
    <img src="https://img.shields.io/badge/Rendering-8A2BE2?style=for-the-badge&logoColor=white" />
</div>

### ハイライト

- Vulkanやレンダリング技術の学習のためにC++でゲームエンジンを開発
- **Blinn–Phong反射モデル** を使用した3D Vulkanレンダラーを実装
- CMakeビルドシステムとGLSLシェーダーコンパイルを統合
- **OBJメッシュローディング**、**ゲームタイムシステム**、**マウス/キーボード入力** を追加

<img src="/img/XenonVk/lge_demo.gif" width="800" alt="簡単なデモ"/>

<div style="display: flex; gap: 20px; flex-wrap: wrap;">
    <img src="/img/XenonVk/wireframe3.png" width="350" alt="ワイヤーフレーム"/>
    <img src="/img/XenonVk/lge_latest.png" width="350" alt="複雑なシーン"/>
</div>

### 参考文献

- [Brendan Galea: LittleVulkanEngine](https://youtu.be/Y9U9IE0gVHA?si=42keJCaEPE-R697P)
- <https://gameprogrammingpatterns.com/>
- _Game Engine Architecture_ by Jason Gregory
- _Game Physics Engine Development_ by Ian Millington
- <https://learnopengl.com/>

----

## 3. その他のプロジェクト

### A\) [アポロニアンガスケットジェネレーター *(Rhinoceros/Python)*](https://github.com/WvXY/_TinyProjects/tree/master/ApollonianGasket)

<div style="display: flex; gap: 2px; flex-wrap: wrap;">
    <img src="/img/small/ap.gif" height="142"/>
    <img src="/img/small/1.jpg"  height="142"/>
    <img src="/img/small/2.jpg"  height="142"/>
    <img src="/img/small/3.png"  height="142"/>
    <img src="/img/small/6.png"  height="142"/>
</div>


### B\) [Voronoi図の実験ツール *(Python/GLSL)*](https://github.com/WvXY/_toolkitPy/blob/main/demos/voronoi_interactive.py)

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

---

以上になります。ご覧いただきありがとうございます!!

<!-- Thank you for reading! -->
