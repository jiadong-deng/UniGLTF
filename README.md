# UniGLTF

[glTF](https://github.com/KhronosGroup/glTF) importer and exporter

* Unityt5.6.3
* glTF-2.0

![duck](doc/duck.png)
![duck_prefab](doc/duck_prefab.png)
![animation](doc/animation.gif)

* [Sample and Tests](https://github.com/ousttrue/UniGLTF_Test)
* [Humanoid Helper](https://github.com/ousttrue/UniHumanoid)
* [Json backend](https://github.com/ousttrue/UniJson)

# License

* [MIT license](LICENSE)

# Sample Models

* https://github.com/KhronosGroup/glTF-Sample-Models

Exclude SciFiHelmet(70074vertices), all model can import.

[Mesh.IndexFormat(from 2017.3)](https://docs.unity3d.com/ScriptReference/Mesh-indexFormat.html) allows a huge mesh, Otherwise mesh division required.

![SciFiHelmet](doc/SciFiHelmet.png)

# Download

* https://github.com/ousttrue/UniGLTF/releases

## Install

* import [unitypackage](https://github.com/ousttrue/UniGLTF/releases)

# Usage

## Import as asset

* drop gltf folder or glb file into Assets folder

or

* menu [UniGLTF] - [Import] (select out of Asset folder gltf file(gltf, glb, zip) and (save into Asset folder) 

## Import in runTime

```cs
var path; // gltf, glb or zip(include gltf)

var context = gltfImporter.Load(path);
context.ShowMeshes();

GameObject root = context.Root;
```

## Export from scene

* menu [UniGLTF] - [Export]

## Import in runTime

```cs
var gltf = new glTF();
using (var exporter = new gltfExporter(gltf))
{
    exporter.Prepare(go);
    exporter.Export();
}
var bytes = gltf.ToGlbBytes();
File.WriteAllBytes(path, bytes);
```

