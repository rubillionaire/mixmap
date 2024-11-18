# 1.7.0

- [map] allow map to accept an object at the `attributes` key that get merged into the props used to render the map's containing div. immediately useful for addorning the map with touch events, among other things
- [map] check for `clear` object on `mix.create` call, if defined, use that object as the argument for the `regl.clear` call in `map.draw`. immediately useful for opting into using the stencil buffer and being able to clear it.
- [map] add `draw:end` event to the end of the `map.draw` method.
- [index] add a `draw` function to `MixMap` prototype, so that we can draw all of our maps at once as determined by an outside observer.
- [package] add a `browser` field with multiple exports, so that `Map` and `Draw` can be modified by the user if needed.
- [index] migrate to `@rubenrodriguez/regl-component` which exposes the underlying regl subcontexts, so that we can coordinate the tick timing of external components with the tick timing of individual draw calls.
- [draw] `_run` accepts common map props, and spreads them across the draw command's props. the combination of these props is now done with a new `xprops` variable that repsents the merger of these two sets of props, instead of merging the map props with the draw props. this ensures that the combined props are always reflective of the latest merger of props, removing bugs from use cases that coordinated multiple maps with different map props such as distinct viewport values.


# v1.6.1

- fork and scope package for continued updates, it seems the original maintainers are no longer active.
