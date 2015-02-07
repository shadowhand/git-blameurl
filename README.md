# git-blameurl

Get the Github blame URL for any file in the repository. Works best when combined with other scripts.

## Examples

```bash
git blameurl
git blameurl public/index.html
```

### On Mac

git-blameurl works very well with the `open` command:

```bash
open $(git blameurl)
open $(git blameurl public/index.html)
```

#### With VIM

Can be used with VIM to open a file at a given line:

```vim
" Copy the current blame url for this file/line
command! -nargs=0 CopyBlameURL exe "!echo $(git blameurl %)\\\#L" . line(".") . " | pbcopy"

" Open the blame url for this file/line
command! -nargs=0 OpenBlameURL exe "!open $(git blameurl %)\\\#L" . line(".")
```
