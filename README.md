# Gotchas:
## Materials:
- Tiny is using `Unity.Tiny.Rendering.MeshRenderer` while Editor is using `Unity.Rendering.RenderMesh`. If you want to
change materials at runtime, use two systems

## Audio
- To run an audio, use `AudioSourceStart`. `Play On Awake` is adding this component automatically, but it needs
to be added only after the first input from the user (browser restriction).

## Misc
- `IJobForEach<T>` works in editor with Tag components, but not in DOTS runtime >> replace with Entities.WithAll<T>.ForEach
- Remember to always use `RequireSingletonForUpdate<T>()` in `OnStartRunning()` / `OnCreate()` when using singleton
- The game is blocking event propagation, listen for JS events on canvas level.