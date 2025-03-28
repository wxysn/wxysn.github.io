---
title: "ポートフォリオ"
description: "個人のプロジェクトの紹介と成果物のデモ"
date: 2025-03-28
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

- **Python** を用いて，間取り設計の最適化のためのドア配置最適化プログラムを開発
- 大規模な人の流れシミュレーションのために，**2Dナビゲーションメッシュ（半エッジメッシュ，A\*経路探索，ファンネルアルゴリズム）** をゼロから実装
- **動的メッシュの切断/統合操作** と **履歴追跡** を活用したランタイム最適化システムを設計
- 高速処理のためにデータ指向設計(DOD)を適用

### Demo

<div style="display: flex; gap: 2px; flex-wrap: wrap;">
    <img src="/img/door_opti/case3.gif" width="355" alt="ケース1"/>
    <img src="/img/door_opti/case2.gif" width="355" alt="ケース2"/>
</div>

### 結果
<img src="/img/door_opti/ress.svg"/>

### 苦労した部分

{{< toggle title="動的なメッシュ処理" >}}

<strong>関連コード：</strong>  
<code>u_geometry.py</code>, <code>g_mesh.py</code>, <code>s_door_system.py</code>  

<br>  
Half–edge 構造に対して，基本的な操作を2種類実装した：  
Edge を<strong>切断</strong>する操作と，Edge を<strong>統合</strong>する操作．  
メッシュを更新する際に構造を壊さず，元のメッシュ情報を保持することが重要だった．  
<br>  

<strong>Half–edge 構造の活用：</strong>  
<ul>
    <li>各 Edge に探索を効率化する情報（例：面，対角の頂点など）を組み込む．</li>
    <li>ジオメトリーの管理やデバッグを容易にするため,ジオメトリーに ID を付与し，デバッグ描画で確認できるようにした．</li>
</ul>

<br>  

<strong>履歴機能の実装：</strong>  
<ul>
    <li>一連の更新を行っても，元の Edge を保存できるようにする．</li>
    <li>ジオメトリーの変更を追跡するために,履歴機能を導入．</li>
    <li>履歴機能では,初期の Edge と Edge 上の位置（0–1）を記録することで，変更を管理できる．</li>
</ul>

<br>  
<img src="/img/door_opti/dbg.gif" alt="Debug Draw"/>  
🔼 デバッグ描画では，ドアコンポーネントを Edge 上で時計回りに移動させながら，
動的にメッシュを<strong>切断/統合</strong>しているが，初期に作成したジオメトリーの情報が保持されている．  

{{< /toggle >}}

### 注目すべき部分

{{< toggle title="ナビゲーションメッシュの実装" >}}

<strong>関連コード：</strong>  
<code>u_cdt.py</code>, <code>u_path_finding.py</code>, <code>g_navmesh.py</code>  

<br>  
カスタマイズ性を重視し，ゼロからナビゲーションメッシュを実装することにした．  
ナビゲーションメッシュの実装には，メッシュの構築，A*経路探索，ファンネルアルゴリズムの実装など，多くの技術的課題があった．  
特に,ファンネルアルゴリズムの実装では，複雑なエッジケースが多く，デバッグが困難だった．  
<br>  

<strong>実装の流れ：</strong>  
<ol>
    <li>
        <strong>2Dメッシュの構築</strong><br>
        CDT（Constrained Delaunay Triangulation）ライブラリのPython Bindingを使用して実装した．<br>
        生成したメッシュを前処理として Half-edge 構造に変換し，各 Edge に種類情報やフラグを記録することで，  
        その後の最適化処理をスムーズかつ高効率に実行できるようにする．
    </li>
    <li>
        <strong>A*経路探索の実装</strong><br>
        メッシュの面（三角形）上で最短の三角形ルートを探索する．
    </li>
    <li>
        <strong>ファンネルアルゴリズムの適用</strong><br>
        A*で求めた三角形ルートに基づき，ファンネルアルゴリズムを使用して最適な移動経路を計算する．
    </li>
</ol>

{{< /toggle >}}

<!-- ＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝＝ -->

{{< toggle title="ランタイム最適化アルゴリズム" >}}
<strong>関連コード：</strong>  
<code>u_loader.py</code>, <code>s_***.py</code>, <code>o_optimizer.py</code>, <code>f_layout.py</code>  

<br>  
　本プログラムは,動線を考慮した間取り最適化を目的とし，サンプリング点を設定して人の動線をシミュレーションする．  
平均移動距離をロス関数とし，ドアの配置を最適化することを主眼としている．  
<br>  

<strong>最適化の手順：</strong>  
<ol>
    <li>
        <strong>初期設定の読み込み</strong><br>
        ドアの初期設定,部屋の接続要件，および最適化パラメータをTOMLファイルに記述し，プログラムに読み込む．<br>
        Flood Algorithm を用いてメッシュ上の閉領域を検出し，部屋の接続要件を自動生成する．
    </li>
    <li>
        <strong>最適化処理</strong><br>
        接続条件を基にドアの初期配置を自動生成する．<br>
        その後，MCMC（Markov Chain Monte Carlo）アルゴリズムを適用し，ドアの位置を動的に変更しながら最適な配置を探索する．
    </li>
    <li>
        <strong>最適配置の確定と履歴管理</strong><br>
        最適なドア配置が決定した後，メッシュデータを更新し，最適化結果を反映する．<br>
        さらに，履歴管理機能を活用して変更を追跡し，最適な配置を維持できるようにする．
    </li>
</ol>
{{< /toggle >}}


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
- **OBJメッシュローディング**，**ゲームタイムシステム**，**マウス/キーボード入力** を追加

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

以上になります．ご覧いただきありがとうございます!!

<!-- Thank you for reading! -->
