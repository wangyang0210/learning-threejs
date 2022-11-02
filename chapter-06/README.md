# chapter-06

> 光照

## AmbientLight

> https://threejs.org/docs/#api/zh/lights/AmbientLight

环境光会均匀的照亮场景中的所有物体。环境光不能用来投射阴影，因为它没有方向。

## HemisphereLight

> https://threejs.org/docs/#api/zh/lights/HemisphereLight

光源直接放置于场景之上，光照颜色从天空光线颜色渐变到地面光线颜色。半球光不能投射阴影。

## DirectionalLight

> https://threejs.org/docs/#api/zh/lights/DirectionalLight

平行光是沿着特定方向发射的光。这种光的表现像是无限远,从它发出的光线都是平行的。常常用平行光来模拟太阳光的效果，平行光可以投射阴影;

## PointLight

> https://threejs.org/docs/#api/zh/lights/PointLight

从一个点向各个方向发射的光源。一个常见的例子是模拟一个灯泡发出的光，该光源可以投射阴影。

## SpotLight

> https://threejs.org/docs/#api/zh/lights/SpotLight

光线从一个点沿一个方向射出，随着光线照射的变远，光线圆锥体的尺寸也逐渐增大，该光源可以投射阴影。

## RectAreaLight

> https://threejs.org/docs/#api/zh/lights/RectAreaLight

平面光光源从一个矩形平面上均匀地发射光线。这种光源可以用来模拟像明亮的窗户或者条状灯光光源。

注意事项:

-   不支持阴影。
-   只支持 MeshStandardMaterial 和 MeshPhysicalMaterial 两种材质。
-   你必须在你的场景中加入 RectAreaLightUniformsLib ，并调用 init()。
