# Wallpaper Engine PKG 壁纸提取与场景还原工具

一个无需安装、无需后端、可直接在浏览器中离线运行的 Wallpaper Engine / PKG 资源解析工具。

项目主要用于从 PKG 资源包或 MP4 文件中提取壁纸素材，并尽可能还原 Wallpaper Engine 场景中的最终静态壁纸效果。所有解析均在浏览器本地完成，文件不会上传到服务器。

## 项目特点

- **纯前端离线运行**：打开 `index.html` 即可使用，无需 Python、Node.js 或其他运行环境。
- **支持 PKG 资源包解析**：可识别 `PKGV0018`、`PKGV0020` 等资源包结构。
- **图片资源提取**：识别 PNG、JPEG、WebP、GIF 等嵌入资源，并优先保留高分辨率素材。
- **Wallpaper Engine 场景还原**：读取 `scene.json`，根据图层位置、缩放、旋转、透明度及顺序合成最终静态壁纸。
- **Puppet Warp 骨骼还原**：针对部分角色/骨骼动画素材，可解析 MDL 网格、骨骼和参考动画姿态，通过 WebGL 重建静态角色画面，而不是简单把分离素材直接拼接。
- **MP4 视频壁纸支持**：识别 MP4 视频资源，可保留原视频并自动生成 PNG 封面。
- **批量处理**：支持一次拖入多个 PKG / MP4 文件。
- **结果预览与导出**：支持预览、单独下载、逐张下载以及 ZIP 打包。
- **素材层查看**：场景合成后可以按需查看原始素材图层。
- **深色 / 浅色主题**：支持界面主题切换并保留本地设置。
- **隐私友好**：解析过程全部在本机浏览器执行，不向远程服务器上传文件。

## 适用场景

这个项目适合用于：

1. 从 Wallpaper Engine 相关 PKG 资源中提取原始壁纸图片；
2. 将一个场景中分散的纹理图层重新合成为完整静态壁纸；
3. 处理由多张 PNG、纹理图或 Puppet Warp 角色素材组成的动态壁纸资源；
4. 从视频壁纸中提取原始 MP4 和静态封面；
5. 对壁纸资源包进行快速浏览、整理和本地导出。

## 使用方法

1. 下载本项目；
2. 使用 Chrome、Edge 等现代浏览器直接打开 `index.html`；
3. 将 `.pkg` 或 `.mp4` 文件拖入页面，或点击“选择文件”；
4. 等待本地解析；
5. 在结果区域查看提取素材或最终合成壁纸；
6. 根据需要单独下载或批量打包。
<img width="2560" height="2297" alt="image" src="https://github.com/user-attachments/assets/638421e6-5a8c-469e-bc08-9d19bc1ad0b2" />

## 技术实现

项目为单文件 HTML 应用，主要使用：

- HTML / CSS / JavaScript
- Canvas 2D
- WebGL
- 浏览器 File / Blob / Object URL API
- 自定义二进制格式解析
- Wallpaper Engine 场景数据解析
- MDL 网格与骨骼姿态静态渲染

无需安装第三方依赖。

## 项目定位

本项目更接近一个 **Wallpaper Engine 资源提取器 + 静态场景还原器**。

与只扫描 PKG 文件中 PNG/JPG 文件头的简单提取工具相比，本项目还会尝试理解场景配置、纹理引用、图层关系及 Puppet Warp 网格数据，从而还原出更接近原始壁纸展示效果的最终图片。

## 注意事项

- 不同 Wallpaper Engine 项目可能使用不同资源格式、特效、着色器或运行时逻辑，因此并非所有动态效果都能完整转换为静态图片。
- 粒子、实时着色器、音频响应、复杂脚本和部分特殊特效通常无法在纯静态导出中完全复现。
- 本工具主要面向用户本人拥有或有权处理的壁纸资源，请遵守相关素材版权及平台规则。

## 文件结构

```text
Wallpaper-PKG-Extractor/
├── index.html      # 主程序，浏览器直接打开
└── README.md       # 中文项目说明
```

## 运行环境

推荐：

- Google Chrome
- Microsoft Edge
- 其他支持现代 JavaScript、Canvas 和 WebGL 的 Chromium 系浏览器

## 项目名称

**Wallpaper-PKG-Extractor**

中文名称：**Wallpaper Engine PKG 壁纸提取与场景还原工具**

## 一句话介绍

> 一个纯浏览器、完全离线的 Wallpaper Engine PKG / MP4 壁纸资源提取与静态场景还原工具，支持 scene.json 图层合成和 Puppet Warp 骨骼网格还原。
