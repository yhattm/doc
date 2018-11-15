move word: w, b
move line: ^, $, enter, delete, (), {}
move: gg, H, M, L, G
Press Ctrl-o to jump back to the previous location.
Press Ctrl-i (same as Tab) to jump forward to the next location.

Joint line: J
replace: r, R, cc, cw
shift: >>, <<
find: /, ?
find word: *, #

:[range]s/pattern/string/[c,e,g,i]

mark: mx, `x, 'x

select: ctrl v

# vimdiff
:dp (diffput)
:dg (diffget)
Ctrl-w, w
:diffupdate
:qa
:wa
:qwa
:qa!
