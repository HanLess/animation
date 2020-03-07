<a href="https://cloud.tencent.com/developer/article/1543647">ThreeJS 不可忽略的事情 - Gamma色彩空间</a>

### GLTF 格式文件

纹理中包含的颜色信息（.map, .emissiveMap, 和 .specularMap）在glTF中总是使用sRGB颜色空间，而顶点颜色和材质属性（.color, .emissive, .specular） 则使用线性颜色空间。在典型的渲染工作流程中，纹理会被渲染器转换为线性颜色空间，进行光照计算，然后最终输出会被转换回 sRGB 颜色空间并显示在屏幕上。除非你需要使用线性颜色空间进行后期处理，否则请在使用glTF的时候将WebGLRenderer进行如下配置：

```
renderer.outputEncoding = THREE.sRGBEncoding;
```

当从外部加载纹理（例如，使用TextureLoader）并将纹理应用到glTF模型，则必须给定对应的颜色空间与朝向：

```
// If texture is used for color information, set colorspace.
texture.encoding = THREE.sRGBEncoding;

// UVs use the convention that (0, 0) corresponds to the upper left corner of a texture.
texture.flipY = false;
```
