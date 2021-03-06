# Getting Started

[[toc]]

::: danger New version
Photo Sphere Viewer 4 is not compatible with previous versions. If you are using version 3 , please follow the [migration guide](./migration-v3.html). You can also read the [version 3 documentation](https://photo-sphere-viewer-3.netlify.com).
:::

## Install Photo Sphere Viewer

#### With npm or yarn

```bash
npm install photo-sphere-viewer

yarn add photo-sphere-viewer
```

#### Via CDN

Photo Sphere Viewer is available on [jsDelivr](https://cdn.jsdelivr.net/npm/photo-sphere-viewer/dist/)

#### Manually

You can also [download the latest release](https://github.com/mistic100/Photo-Sphere-Viewer/releases)

## Dependencies

#### Required
 * [three.js](https://threejs.org)
 * [uEvent 2](https://github.com/mistic100/uEvent)

#### Optionals
 * [promise-polyfill](https://github.com/taylorhakes/promise-polyfill) for IE compatibility


## Your first viewer

Include all JS & CSS files in your page manually or with your favorite bundler and init the viewer.

The `panorama` must be an [equirectangular projection](https://en.wikipedia.org/wiki/Equirectangular_projection) of your photo. You can also use [cubemap projection](cubemap) with a special syntax.

```html
<div id="viewer"></div>

<style>
  #viewer {
    width: 100vw;
    height: 50vh;
  }
</style>

<script>
  const viewer = new PhotoSphereViewer.Viewer({
    container: document.querySelector('#viewer'),
    panorama: 'path/to/panorama.jpg'
  });
</script>
```

::: tip Cropped panoramas
If your image is not covering a full 360°×180° sphere, it will be deformed. You can fix it by providing [cropping data](./cropped-panorama).
:::

::: tip Caching
Previous version of Photo Sphere Viewer had a caching system, which was buggy and thus disabled by default.

Photo Sphere Viewer 4 uses [THREE.js Cache](https://threejs.org/docs/index.html#api/en/loaders/Cache), enabled by default. You can disable this cache by calling `THREE.Cache.enabled = false;` after importing Photo Sphere Viewer.
:::
