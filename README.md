# Best-VIM-Setup
## for Python

Vim config:
```
syntax on

set expandtab
set smarttab
set tabstop=4
set softtabstop=4
set shiftwidth=4
set number

set noerrorbells
set novisualbell

" enable mouse
set mouse=a

" auto close brackets
inoremap " ""<left>
inoremap ' ''<left>
inoremap ( ()<left>
inoremap [ []<left>
inoremap { {}<left>
inoremap {<CR> {<CR>}<ESC>O
inoremap {;<CR> {<CR>};<ESC>O

call plug#begin()
Plug 'davidhalter/jedi-vim'
Plug 'joshdick/onedark.vim'
call plug#end()

" Atom dark theme
if (empty($TMUX))
  if (has("nvim"))
    "For Neovim 0.1.3 and 0.1.4 < https://github.com/neovim/neovim/pull/2198 >
    let $NVIM_TUI_ENABLE_TRUE_COLOR=1
  endif
  "For Neovim > 0.1.5 and Vim > patch 7.4.1799 < https://github.com/vim/vim/commit/61be73bb0f965a895bfb064ea3e55476ac175162 >
  "Based on Vim patch 7.4.1770 (`guicolors` option) < https://github.com/vim/vim/commit/8a633e3427b47286869aa4b96f2bfc1fe65b25cd >
  " < https://github.com/neovim/neovim/wiki/Following-HEAD#20160511 >
  if (has("termguicolors"))
    set termguicolors
  endif
endif


colorscheme onedark

" to disable window
autocmd FileType python setlocal completeopt-=preview

" Flake8 linting automaticly
autocmd BufWritePost *.py call flake8#Flake8()

```

Also install extensions (follow tutorials):
- https://github.com/airblade/vim-gitgutter
- https://github.com/nvie/vim-flake8


In the end of this repo, I want to say that VS Code greater then vim :)
But for old PCs and servers vim is great
