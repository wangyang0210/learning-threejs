# chapter-05

> 纹理

## TextureLoader

> https://threejs.org/docs/#api/zh/loaders/TextureLoader

单个纹理加载，加载 texture 的一个类。 内部使用 ImageLoader 来加载文件。

```
const texture = loader.load('resources/images/flower-1.jpg');
```

使用上面的方式直接加载我们的纹理将是透明的，直到图片被 three.js 异步加载完成，这时它将用下载的图片更新纹理。这有一个很大的好处，就是我们不必等待纹理加载，我们的页面会立即开始渲染,如果你想等纹理加载完成再开始渲染的话,可以给 load 添加一个回调，等纹理加载完成再开始渲染。

```
const texture = loader.load('resources/images/flower-1.jpg', (texture) =>{
    // 省略代码
});
```

## LoadingManager

> https://threejs.org/docs/#api/zh/loaders/managers/LoadingManager

创建一个并将其传递给 TextureLoader，然后将其 onLoad 属性设置为回调

```
 loadManager.onLoad = () => {
                const cube = new THREE.Mesh(geometry, materials)
                scene.add(cube)
                cubes.push(cube) // 添加到我们要旋转的立方体数组中
            }
```
