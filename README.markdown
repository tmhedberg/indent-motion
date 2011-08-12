indent-motion
=============

indent-motion is a Vim plugin which maps `<Leader>[` and `<Leader>]` in normal, visual, and operator-pending modes to move to the beginning and end (respectively) of your current indentation-delimited block (`<Leader>` refers to your current user-defined "mapleader", which is `\` by default).

For example (using JavaScript):

    function foo(a, b, c) {
        var x = 1;
        var y = 2;
        if (x == y) {
            alert("This will never happen!");
            ++y;
        }
    }

In the above snippet, if the cursor is positioned on the `var x = 1;` line, then `<Leader>]` will move the cursor to the next-to-last line (closing brace of the conditional block) and `<Leader>[` will move it back to the original location. If the cursor is positioned on the `alert` call, then `<Leader>]` will move down 1 line to `++y;`.

If one of the mappings is executed on an empty line (containing no characters, not even whitespace), then the assumed indentation will be that of the next non-empty line, where "next" is in the direction of the requested motion.

Currently, the mappings are not configurable, but this can easily be changed upon request.
