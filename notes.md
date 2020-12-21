# Notes

## Open new terminal in same directory

A new terminal should open in the last directory we cd'ed in. For that, we could
use a FIFO file. This let us exchange information between two processes without
making unnecessary i/o on the filesystem.

## Compact PATH

The `compact_cwd` function need to be rewritten. We could integrate it more
tightly with the `cwd` function. Here's a list of possible mode that could be
supported:

- absolute: this is the default behavior of `\w`.
- relative: this is the default behavior of `\w`.
- truncate: We use `PROMPT_DIR=N` to truncate `\w` by Nth folder from the start.
- absolute-compact: We only show the first character of each folder except for
                    the last one that is extended. We also show two characters
                    for folders that begin with a special character like hidden
                    folders.
- truncate-compact: Same as absolute-compact but we truncate the path before
                    applying the compact styling.

## VCS

It should show when a Mercurial repository has been modified. We could also add
more options for both Git and Mercurial
