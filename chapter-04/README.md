# chapter-04

TODO 每种材质独立的案例 demo

> 材质

## MeshBasicMaterial

> https://threejs.org/docs/#api/zh/materials/MeshBasicMaterial

不受光照影响

## MeshLambertMaterial

> https://threejs.org/docs/#api/zh/materials/MeshLambertMaterial

只在顶点计算光照

## MeshPhongMaterial

> https://threejs.org/docs/#api/zh/materials/MeshPhongMaterial

每个像素计算光照,支持镜面高光

## MeshToonMaterial

> https://threejs.org/docs/#api/zh/materials/MeshToonMaterial

MeshToonMaterial 不是平滑地着色，而是使用一个渐变图（一个 X 乘 1 的纹理（X by 1 texture））来决定如何着色。默认使用的渐变图是前 70%的部分使用 70%的亮度，之后的部分使用 100%的亮度，当然，你可以定义你自己的渐变图。这最终会给人一种 2 色调的感觉，看起来就像卡通一样。

## MeshStandardMaterial

> https://threejs.org/docs/#api/zh/materials/MeshStandardMaterial

MeshStandardMaterial 基于物理的渲染（PBR），提供了比 MeshLambertMaterial 或 MeshPhongMaterial 更精确和逼真的结果，代价是计算成本更高。

## MeshPhysicalMaterial

> https://threejs.org/docs/#api/zh/materials/MeshPhysicalMaterial

MeshStandardMaterial 的扩展，提供了更高级的基于物理的渲染属性：

Clearcoat: 有些类似于车漆，碳纤，被水打湿的表面的材质需要在面上再增加一个透明的，具有一定反光特性的面。而且这个面说不定有一定的起伏与粗糙度。Clearcoat 可以在不需要重新创建一个透明的面的情况下做到类似的效果。
基于物理的透明度:.opacity 属性有一些限制:在透明度比较高的时候，反射也随之减少。使用基于物理的透光性.transmission 属性可以让一些很薄的透明表面，例如玻璃，变得更真实一些。
高级光线反射: 为非金属材质提供了更多更灵活的光线反射。
Sheen: Can be used for representing cloth and fabric materials.
物理网格材质使用了更复杂的着色器功能，所以在每个像素的渲染都要比 three.js 中的其他材质更费性能，大部分的特性是默认关闭的，需要手动开启，每开启一项功能在开启的时候才会更耗性能。请注意，为获得最佳效果，您在使用此材质时应始终指定 environment map。

> 各种标准材质的构建速度从最快到最慢：MeshBasicMaterial ➡ MeshLambertMaterial ➡ MeshPhongMaterial ➡ MeshStandardMaterial ➡ MeshPhysicalMaterial。构建速度越慢的材质，做出的场景越逼真，但在低功率或移动设备上，你可能需要思考代码的设计，使用构建速度较快的材质。

## MeshDepthMaterial

> https://threejs.org/docs/#api/zh/materials/MeshDepthMaterial

MeshDepthMaterial 渲染每个像素的深度，其中处在摄像机负近端面的像素其深度为 0，处在摄像机负远端面的像素其深度为 1。

## MeshNormalMaterial

> https://threejs.org/docs/#api/zh/materials/MeshNormalMaterial

MeshNormalMaterial 会绘制视图空间法线（相对于摄像机的法线）。x 是红色, y 是绿色, 以及 z 是蓝色，所以朝向右边的东西是粉红色，朝向左边的是水蓝色，朝上的是浅绿色，朝下的是紫色，朝向屏幕的是淡紫色

## ShaderMaterial

> https://threejs.org/docs/#api/zh/materials/ShaderMaterial

ShaderMaterial 是通过 three.js 的着色器系统来制作自定义材质。

## RawShaderMaterial

> https://threejs.org/docs/#api/zh/materials/RawShaderMaterial

RawShaderMaterial 是可以用来制作完全自定义的着色器，不需要 three.js 的帮助。
