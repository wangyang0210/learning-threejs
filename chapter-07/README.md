# chapter-07

> 照相机

## PerspectiveCamera

> https://threejs.org/docs/#api/zh/cameras/PerspectiveCamera

这一投影模式被用来模拟人眼所看到的景象，它是 3D 场景的渲染中使用得最普遍的投影模式。

PerspectiveCamera 通过四个属性来定义一个视锥. near 定义了视锥的前端, far 定义了后端, fov 是视野, 通过计算正确的高度来从摄像机的位置获得指定的以 near 为单位的视野, 定义的是视锥的前端和后端的高度. aspect 间接地定义了视锥前端和后端的宽度, 实际上视锥的宽度是通过高度乘以 aspect 来得到的.

## OrthographicCamera

> https://threejs.org/docs/#api/zh/cameras/OrthographicCamera

在这种投影模式下，无论物体距离相机距离远或者近，在最终渲染的图片中物体的大小都保持不变。这对于渲染 2D 场景或者 UI 元素是非常有用的。
