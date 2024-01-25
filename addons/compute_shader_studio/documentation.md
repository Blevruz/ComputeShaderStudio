
# Variables available in the GLSL code

- `uint x,y` : from `GlobalInvocationID.x` and `.y`
- `uint p` : the position `[x][y]` in the invocation
- `uint WSX, WSY` : the Global WorkSpace of invocations (generally match the data size)
- `int* data_0, data_1, etc` : are the data treated (can be displayed by Sprite2D, TextureRect, etc). Access them by `data_0[p]`, `data_1[p]`, etc
- `uint step` : simulation step of the execution. Increased by 1 after `nb_passes`
- `uint nb_passes`: the number of passes your code needs (by step). There is a barrier between each pass.
- `uint current_pass`: pass currently executed (one pass per frame, `nb_passes` by step)

# How the buffers are initialized

When not in preset mode, each value / pixel is set with `randi_range()` to a random value between 0 and 100.
When in preset mode, the buffer is initialized with the first image in Data.
