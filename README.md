This is a reproduction of [issue #241 in the `phantom-camera` Godot addon](https://github.com/ramokz/phantom-camera/issues/241)

There are two plugins installed:

- [`phantom-camera`](https://github.com/ramokz/phantom-camera)
- [`smoothing-addon`](https://github.com/lawnjelly/smoothing-addon)

The physics tick rate is set to 10 so that the visual representation of the player lags behind the physics object.

In [`character.gd`](./character.gd) there is the default script for `CharacterBody3D` that moves the `RigidBody3D` around using the arrow keys, with space bar to jump.

The scene has the following layout:

- `CharacterBody3D`: The node we want to follow with the camera
  - `CollisionShape3D`: Capsule collision shape
  - `Smoothing`: From the [`smoothing-addon`](https://github.com/lawnjelly/smoothing-addon)
    - `MeshInstance3D`: Visual representation of the collision shape
- `SimpleFollowCamera`: Phantom camera set to follow `MeshInstance3D`
- `StaticCamera`: Phantom camera not following anything
  - Set the `Priority` to switch cameras and see different behavior
- Some random objects so you can see the character moving around
