# Context

A running instance of ProdUI. Nearly all UI state and data is stored in this table.


## Scope

While not a global variable, the context is passed around to so many files that it is often treated like one. It is also, technically, not a singleton, but most applications will only have the need for one context.


## Paths

Some functions can interpolate symbols into paths. The symbol `%produi%` is built in, and by default, it will always point to the ProdUI directory. The library user can add more path symbols by editing the table `context.path_symbols`.

### Warning

The editing of paths should happen before any resources are loaded, probably just after making the context. Changing paths after anything has been instantiated will cause problems.
