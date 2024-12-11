# 1.8.0

- [map] minor: emit `draw:start` in addition to draw:end. this happens after the regl canvas is cleared.
- [package] bump to `@rubenrodriguez/regl-component@1.2.10` to make use to of the `IntersectionObserver` API, reducing the number of times we need to `getBoundingClientRect`.
- [map] patch: remove the redraw on scroll and resize because regl component is already doing this for us.
- [map] minor: `map.pick` options, allow author to define `opts.fbWidth` & `opts.fbHeight` if they want to manipulate the size of the picking renderbuffer. this is used in `mixmap-georender` to allow for doubling the canvas size in order to store more data per pixel in the pick buffer. there is also an opportunity to define additional props into the pick's draw command via `opts.props`.
- [map] patch: `map.pick` reset `map._pickInit` to false on map's `resize` event.

# 1.7.1

- [index] remove the `scroll` & `resize` handlers, these are already accounted for in `regl-component` and its multi-regl (`multi`) implementation.

# 1.7.0

- [map] allow map to accept an object at the `attributes` key that get merged into the props used to render the map's containing div. immediately useful for addorning the map with touch events, among other things
- [map] check for `clear` object on `mix.create` call, if defined, use that object as the argument for the `regl.clear` call in `map.draw`. immediately useful for opting into using the stencil buffer and being able to clear it.
- [map] add `draw:end` event to the end of the `map.draw` method.
- [index] add a `draw` function to `MixMap` prototype, so that we can draw all of our maps at once as determined by an outside observer.
- [package] add a `browser` field with multiple exports, so that `Map` and `Draw` can be modified by the author if needed.
- [index] migrate to `@rubenrodriguez/regl-component` which exposes the underlying regl subcontexts, so that we can coordinate the tick timing of external components with the tick timing of individual draw calls.
- [draw] `_run` accepts common map props, and spreads them across the draw command's props. the combination of these props is now done with a new `xprops` variable that repsents the merger of these two sets of props, instead of merging the map props with the draw props. this ensures that the combined props are always reflective of the latest merger of props, removing bugs from use cases that coordinated multiple maps with different map props such as distinct viewport values.


# v1.6.1

- fork and scope package for continued updates, it seems the original maintainers are no longer active.
