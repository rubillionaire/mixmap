# next

- [map] allow map to accept an object at the `attributes` key that get merged into the props used to render the map's containing div. immediately useful for addorning the map with touch events, among other things
- [map] check for `clear` object on `mix.create` call, if defined, use that object as the argument for the `regl.clear` call in `map.draw`. immediately useful for opting into using the stencil buffer and being able to clear it.
- [map] add `draw:end` event to the end of the `map.draw` method.
- [index] add a `draw` function to `MixMap` prototype, so that we can draw all of our maps at once as determined by an outside observer.
- [package] add a `browser` field with multiple exports, so that `Map` and `Draw` can be modified by the user if needed.


# v1.6.1

- fork and scope package for continued updates, it seems the original maintainers are no longer active.
