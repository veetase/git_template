# Setting up hooks for automatic tag-generation using ctags

_SOURCE: [tpope's blog](http://tbaggery.com/2011/08/08/effortless-ctags-with-git.html)_

- Say this directory is `~/git_template`. Run the following commands:
```
git config --global init.templatedir '~/git_template'
```
Make sure the hook files at `./hooks/` are executable.

- Perform `git init` inside an existing repository to copy the hooks at
  `./hooks/` into `repo/.git/hooks/`.

- You can modify the .git/hooks/ctags as you wish, add your favorate language or add exclude path,
  for example: add --exclude=node_modules to exclude node_modules, more detail can check ctags
    --help.

- Now any new repositories we create or clone will be immediately indexed with
  Ctags (at `repo/.git/tags`) and set up to re-index every time we check out, commit, merge, or
  rebase. Basically, we’ll never have to manually run Ctags on a Git repository
  again.

# Setting ctags to index gems
```
1. gem install gem-ctags
2. .vimrc: Plugin 'tpope/vim-bundler'
3. gem ctags # do the index, can any new installed gem will be index automatically.
