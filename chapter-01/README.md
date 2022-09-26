# 第一章
`Version`: 0.144.0
`官网`: https://threejs.org/
`GitHub`: https://github.com/mrdoob/three.js/
`案例`: https://threejs.org/examples/
`文档`: https://threejs.org/docs/
`手册`: https://threejs.org/manual/
`wiki`: https://github.com/mrdoob/three.js/wiki 
`论坛`: https://discourse.threejs.org/
`stackoverflow`: https://stackoverflow.com/questions/tagged/three.js
`code edit`: https://code.visualstudio.com/
`Plugin`: https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer


## 基础

> https://threejs.org/manual/#en/fundamentals

### 应用结构
![threejs-structure](./static/imgs/threejs-structure.svg)

首先有一个渲染器(Renderer)。这可以说是three.js的主要对象。你传入一个场景(Scene)和一个摄像机(Camera)到渲染器(Renderer)中，然后它会将摄像机视椎体中的三维场景渲染成一个二维图片显示在画布上。

其次有一个场景图 它是一个树状结构，由很多对象组成，比如图中包含了一个场景(Scene)对象 ，多个网格(Mesh)对象，光源(Light)对象，群组(Group)，三维物体(Object3D)，和摄像机(Camera)对象。一个场景(Scene)对象定义了场景图最基本的要素，并包了含背景色和雾等属性。这些对象通过一个层级关系明确的树状结构来展示出各自的位置和方向。子对象的位置和方向总是相对于父对象而言的。比如说汽车的轮子是汽车的子对象，这样移动和定位汽车时就会自动移动轮子。你可以在场景图的这篇文章中了解更多内容。

注意图中摄像机(Camera)是一半在场景图中，一半在场景图外的。这表示在three.js中，摄像机(Camera)和其他对象不同的是，它不一定要在场景图中才能起作用。相同的是，摄像机(Camera)作为其他对象的子对象，同样会继承它父对象的位置和朝向。在场景图这篇文章的结尾部分有放置多个摄像机(Camera)在一个场景中的例子。

网格(Mesh)对象可以理解为用一种特定的材质(Material)来绘制的一个特定的几何体(Geometry)。材质(Material)和几何体(Geometry)可以被多个网格(Mesh)对象使用。比如在不同的位置画两个蓝色立方体，我们会需要两个网格(Mesh)对象来代表每一个立方体的位置和方向。但只需一个几何体(Geometry)来存放立方体的顶点数据，和一种材质(Material)来定义立方体的颜色为蓝色就可以了。两个网格(Mesh)对象都引用了相同的几何体(Geometry)和材质(Material)。

几何体(Geometry)对象顾名思义代表一些几何体，如球体、立方体、平面、狗、猫、人、树、建筑等物体的顶点信息。Three.js内置了许多基本几何体 。你也可以创建自定义几何体或从文件中加载几何体。

材质(Material)对象代表绘制几何体的表面属性，包括使用的颜色，和光亮程度。一个材质(Material)可以引用一个或多个纹理(Texture)，这些纹理可以用来，打个比方，将图像包裹到几何体的表面。

纹理(Texture)对象通常表示一幅要么从文件中加载，要么在画布上生成，要么由另一个场景渲染出的图像。

光源(Light)对象代表不同种类的光。

### PerspectiveCamera

![frustum-3d](./static/imgs/frustum-3d.svg)

> https://threejs.org/docs/#api/en/cameras/PerspectiveCamera

fov是视野范围(field of view)的缩写。上述代码中是指垂直方向为75度。 注意three.js中大多数的角用弧度表示，但是因为某些原因透视摄像机使用角度表示。

aspect指画布的宽高比。我们将在别的文章详细讨论，在默认情况下 画布是300x150像素，所以宽高比为300/150或者说2。

near和far代表近平面和远平面，它们限制了摄像机面朝方向的可绘区域。 任何距离小于或超过这个范围的物体都将被裁剪掉(不绘制)。

这四个参数定义了一个 "视椎(frustum)"。 视椎(frustum)是指一个像被削去顶部的金字塔形状。换句话说，可以把"视椎(frustum)"想象成其他三维形状如球体、立方体、棱柱体、截椎体。

> 近平面和远平面的高度由视野范围决定，宽度由视野范围和宽高比决定。
> 视椎体内部的物体将被绘制，视椎体外的东西将不会被绘制。


![scene-down](./static/imgs/scene-down.svg)

默认向下看 -Z 轴，向上看 +Y 轴。我们将立方体放在原点，因此我们需要将相机从原点向后(+Z轴)移动一点，以便看到创建的物体。

我们能看到摄像机的位置在z = 2。它朝向Z轴负方向。我们的视椎体范围从摄像机前方0.1到5。因为这张图是俯视图，视野范围会受到宽高比的影响。画布的宽度是高度的两倍，所以水平视角会比我们设置的垂直视角75度要大。

### 案例

#### 01.create0cube.html

![threejs-1cube-no-light-scene](./static/imgs/threejs-1cube-no-light-scene.svg)

#### 
