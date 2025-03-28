# Layout

ProdUI uses a tree structure to implement layouts. This layout tree is separate from the widget hierarchy tree. A widget's direct children may be added and removed from nodes in its layout tree without altering the overall tree structure.

Only a few widgets have built-in support for layout trees.


## Node Modes

There are four explicit settings for layout nodes:

* `slice`: Reduces the parent node along one side (left, top, bottom, right), and assigns the taken part to a child.

* `grid`: Fits the child as a grid tile within the parent node.

* `static`: Assigns predetermined coordinates and dimensions to the child, still relative to the parent.

* `null`: No effect.

The root node does not support these settings. Its size is the remainder of whatever has not been taken by slice nodes.


## Diagrams

Here is an example layout with slice nodes.

```
┌┈┈┈┈┈┬┈┈┈┈┈┐
│     │  B  │
│  A  ├┈┈┈┈┈┤
│     │  C  │
└┈┈┈┈┈┴┈┈┈┈┈┘
```

The tree looks like this:

```
A, root
└ B, slice right 50%
  └ C, slice bottom 50%
```


Here is a more convoluted example.

```
┌┈┬┈┬┈┬┈┬┈┐
│A│C│ │ │ │
├┈┼┈┤E│F│G│
│B│D│ │ │ │
└─┴─┴─┴─┴─┘
```

```
  G
  |
+-+-+-+
| | | |
A C E F
| |
B D

G, root
└ A, slice left 20%
  └ B, slice bottom 50%
└ C, slice left 20%
  └ D, slice bottom 50%
└ E, slice left 20%
└ F, slice left 20%
```

