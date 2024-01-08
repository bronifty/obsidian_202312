https://news.ycombinator.com/item?id=33638045

- unisonlang serializes a hash of its syntax tree (raw code - not compiled), which is a tree of other hashes (a composite of codes including dependencies) to remote nodes, which involves - not code being shipped around to be dynamically executed, rather - a closure (function) and all of its transitive dependencies 

dynmically ship code around to be dynamically exeecuted, but you aren't going to also get "and of course ship all the transitive dependencies of this closure

It won't be a serialized version of my entire program and all of its dependencies, it will be a hash of a tree, which is a tree of other hashes.

The remote node can inspect the tree and ask for or gossip to find out the definitions for whatever hashes in that tree it doesn't already know about. It can inspect the node for any forbidden hashes (for example, you can'd do arbitrary IO), then the remote node can evaluate the closure, and return a result.