_Note: this package is not yet released! This means that some of the links below
may not be active yet._

# elm-3d-scene

`elm-3d-scene` is a high-level Elm package for producing 3D graphics, with
support for lighting, shadows and realistic materials:

![Lit scene with shadows](https://ianmackenzie.github.io/elm-3d-scene/images/1.0.0/hable-filmic-tone-mapping-bright.png)

It aims to make creating 3D graphics as easy and enjoyable as possible, without
having to worry about low-level details like shader programs and transformation
matrices.

Any questions/feedback, please open an issue or please reach out in the
**#webgl** channel or to **@ianmackenzie** on the [Elm Slack](https://elmlang.herokuapp.com)!

## Getting started

The best way to start learning the `elm-3d-scene` API is by reading through the
[tutorial](https://github.com/ianmackenzie/elm-3d-scene/blob/master/TUTORIAL.md)
and then checking out the [examples](https://github.com/ianmackenzie/elm-3d-scene/tree/master/examples/README.md).
For more details on any type/function, the [reference documentation](https://elm-doc-preview.netlify.app/?repo=ianmackenzie%2Felm-3d-scene)
is your friend.

![Duckling model](https://ianmackenzie.github.io/elm-3d-scene/images/1.0.0/textured-nonmetal-rough.png)

One important point to understand is that `elm-3d-scene` builds heavily on
several other packages, making extensive use of types and modules from:

  - [`avh4/elm-color`](https://package.elm-lang.org/packages/avh4/elm-color/latest/):
    `Color`
  - [`ianmackenzie/elm-3d-camera`](https://package.elm-lang.org/packages/ianmackenzie/elm-3d-camera/latest/):
    `Camera3d` and `Viewpoint3d`
  - [`ianmackenzie/elm-units`](https://package.elm-lang.org/packages/ianmackenzie/elm-units/latest/):
    `Quantity`, `Length`, `Meters`, `Angle`, `Pixels`, `Luminance`, `Illuminance`,
    `LuminousFlux` and `Temperature`
  - [`ianmackenzie/elm-triangular-mesh`](https://package.elm-lang.org/packages/ianmackenzie/elm-triangular-mesh/latest/):
    `TriangularMesh`
  - [`ianmackenzie/elm-geometry`](https://package.elm-lang.org/packages/ianmackenzie/elm-geometry/latest/):
    `Point3d`, `Vector3d`, `Direction3d`, `LineSegment3d`, `Triangle3d`,
    `Sphere3d`, `Block3d`, `Axis3d`...basically anything ending in `3d` other
    than `Camera3d` and `Viewpoint3d` =)

As a result, to start using `elm-3d-scene` in your own project you will need at
least a decent understanding of those packages as well. Check out their READMEs
and reference documentation for details, but you can probably get a decent sense
of how they work by checking out the [`elm-3d-scene` examples](https://github.com/ianmackenzie/elm-3d-scene/tree/master/examples/README.md).

When installing `elm-3d-scene`, you'll also want to install the above packages:

```text
elm install ianmackenzie/elm-3d-scene
elm install avh4/elm-color
elm install ianmackenzie/elm-3d-camera
elm install ianmackenzie/elm-units
elm install ianmackenzie/elm-triangular-mesh
elm install ianmackenzie/elm-geometry
```

(All of the packages will get downloaded and installed automatically anyways,
since they're dependencies of `elm-3d-scene`, but you'll need to install them
explicitly in your own project so that you can use them directly.)

![Table and chairs](https://ianmackenzie.github.io/elm-3d-scene/images/1.0.0/cloudy-scene.png)

## Climate action

I would like for the projects I work on to be as helpful as possible in
addressing the climate crisis. If

- you are working on a project that helps address the climate crisis (clean
  energy, public transit, reforestation, sustainable agriculture etc.) either as
  an individual, as part of an non-profit organization or even as part of a
  for-profit company, and
- there is a new feature you would find helpful for that work (or a bug you need
  fixed) in any of my open-source projects, then

please [open a new issue](https://github.com/ianmackenzie/elm-3d-scene/issues),
describe briefly what you're working on and I will treat that issue as high
priority.

![Spheres and blocks](https://ianmackenzie.github.io/elm-3d-scene/images/1.0.0/point-light.png)

## Contributing

Contributions are very welcome! Here are some ideas for some that would be very
useful at this stage:

- More examples to add to the `examples` directory, showing how to create
  specific kinds of scenes or how to integrate `elm-3d-scene` with other
  packages, such as:
  - An example combining `elm-3d-scene` and [`elm-gamepad`](https://package.elm-lang.org/packages/xarvh/elm-gamepad/latest/),
    perhaps using the gamepad to walk around a scene
  - An example with shadows cast from a moving light source (I think something
    like a point light flying in and amongst a bunch of cubes could look pretty
    cool)
  - Anything you think would look cool/illustrate part of the API missed by
    other examples/help others understand something you struggled with
- Separate packages that parse different 3D model formats so they can be loaded
  into `elm-3d-scene`, such as [OBJ](https://en.wikipedia.org/wiki/Wavefront_.obj_file),
  [STL](https://en.wikipedia.org/wiki/STL_%28file_format%29) or [DAE](https://en.wikipedia.org/wiki/COLLADA).

  I think it makes sense for each file format to have a dedicated package 
  separate from `elm-3d-scene`. Ideally, I think each package should focus on
  simply parsing a file into a nice Elm data structure (instead of directly into
  an `elm-3d-scene` `Entity`, for example) so that the data could also be used
  in other ways (custom rendering engines, 3D printing, analysis etc.).
  
  Note that some work has already started on [GLTF](https://en.wikipedia.org/wiki/GlTF)
  loading, so reach out to me (**@ianmackenzie**) on the [Elm Slack](http://elmlang.herokuapp.com/)
  if that's something you're interested in working on.

Once the internals of `elm-3d-scene` stabilize a bit, there will be lots more
opportunities to contribute to the core rendering engine, to add features such
as:

- Textured backgrounds ([#53](https://github.com/ianmackenzie/elm-3d-scene/issues/53))
- Rectangular/polygonal light sources ([#41](https://github.com/ianmackenzie/elm-3d-scene/issues/41))
- 3D-rendered text ([#37](https://github.com/ianmackenzie/elm-3d-scene/issues/37))
- Procedural textures ([#22](https://github.com/ianmackenzie/elm-3d-scene/issues/22))
- Debug rendering options ([#21](https://github.com/ianmackenzie/elm-3d-scene/issues/21))
- Funky material types like water and ceramics ([#5](https://github.com/ianmackenzie/elm-3d-scene/issues/5))

For now, though, the internals are changing rapidly enough that
coordination/collaboration on these kinds of issues would be tricky.

![Physics simulation](https://ianmackenzie.github.io/elm-3d-scene/images/1.0.0/physics-background-600px.png)
