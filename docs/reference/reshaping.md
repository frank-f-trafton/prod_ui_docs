# Reshaping

## Widget Reshape Events

* `uiCall_reshapePre`: Emitted first. The widget can halt further reshaping by returning true.

* `uiCall_reshapePost`: Emitted last, after layout updates and the reshaping of descendants.
