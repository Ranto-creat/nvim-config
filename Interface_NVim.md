# Installation

## Go to init.vim

``nvim $HOME\AppData\Local\nvim\init.vim``

## Interface vim

```vim
" Initialise vim-plug
call plug#begin('~/.local/share/nvim/plugged')

" Plugins pour améliorer l'interface
Plug 'gruvbox-community/gruvbox'          " Thème de couleurs
Plug 'itchyny/lightline.vim'              " Barre d'état légère
Plug 'kyazdani42/nvim-web-devicons'       " Icônes pour Neovim
Plug 'ryanoasis/vim-devicons'             " Icônes de fichiers
Plug 'preservim/nerdtree'                 " Explorateur de fichiers
Plug 'tpope/vim-fugitive'                 " Intégration Git
Plug 'junegunn/fzf'                       " Fuzzy Finder
Plug 'junegunn/fzf.vim'                   " Fuzzy Finder pour Vim
Plug 'Yggdroot/indentLine'                " Affichage des indentations
Plug 'vim-airline/vim-airline'            " Barre d'état avancée
Plug 'vim-airline/vim-airline-themes'     " Thèmes pour vim-airline
Plug 'easymotion/vim-easymotion'          " Navigation rapide
Plug 'jiangmiao/auto-pairs'               " Auto fermeture des parenthèses
Plug 'tpope/vim-commentary'               " Commenter facilement le code
Plug 'neoclide/coc.nvim', {'branch': 'release'} " Autocomplétion

" Plugins pour le développement web
Plug 'pangloss/vim-javascript'            " Support JavaScript
Plug 'MaxMEllon/vim-jsx-pretty'           " Support JSX/React
Plug 'leafgarland/typescript-vim'         " Support TypeScript
Plug 'peitalin/vim-jsx-typescript'        " Support TSX
Plug 'yuezk/vim-js'                       " Autocompletion
Plug 'HerringtonDarkholme/yats.vim'       " Typescript highlighting
Plug 'airblade/vim-gitgutter'             " Git integration

call plug#end()

" Activer la numérotation des lignes
set number

" Activer la coloration syntaxique
syntax on

" Utiliser des couleurs 256
set t_Co=256

" Configurer le thème Gruvbox
set background=dark
colorscheme gruvbox

" Configurer Lightline
let g:lightline = {
      \ 'colorscheme': 'gruvbox',
      \ }

" Configurer vim-airline
let g:airline_theme='gruvbox'
let g:airline_powerline_fonts = 1

" Configurer NERDTree
nnoremap <C-n> :NERDTreeToggle<CR>
let NERDTreeShowHidden=1
let NERDTreeMinimalUI=1
let NERDTreeDirArrowExpandable='+'
let NERDTreeDirArrowCollapsible='~'

" Activer les numéros relatifs
set relativenumber

" Activer les lignes d'entrelacement
set cursorline

" Configurer les onglets et les espaces
set tabstop=2
set shiftwidth=2
set expandtab

" Activer les caractères invisibles
set list
set listchars=tab:▸\ ,trail:·,extends:>,precedes:<,nbsp:·

" Augmenter la taille du tampon de défilement
set scrolloff=8

" Utiliser les diviseurs verticaux pour les splits
set splitright
set splitbelow

" Mettre en évidence la recherche
set hlsearch
set incsearch

" Activer le copier-coller avec le système
set clipboard=unnamedplus

" Configuration de la barre d'état lightline
let g:lightline = {
      \ 'colorscheme': 'gruvbox',
      \ 'active': {
      \   'left': [ ['mode', 'paste'], ['readonly', 'filename', 'modified'] ]
      \ },
      \ 'component_function': {
      \   'filename': 'LightlineFilename'
      \ },
      \ }

function! LightlineFilename()
  return expand('%:t') ==# '' ? '[No Name]' : expand('%:t')
endfunction

" Configurer NERDTree pour ouvrir automatiquement
autocmd VimEnter * NERDTree
autocmd BufEnter * if tabpagenr('$') == 1 && bufname() == '' && len(filter(range(1, bufnr('$')), 'buflisted(v:val)')) == 1 | q | endif

" Configuration de vim-airline
let g:airline#extensions#tabline#enabled = 1
let g:airline#extensions#tabline#formatter = 'default'

" Configurer indentLine
let g:indentLine_char = '▏'

" Configuration de EasyMotion
nmap <Leader><Leader>w <Plug>(easymotion-overwin-w)

" Configuration de vim-commentary
nmap gc <Plug>Commentary
vmap gc <Plug>Commentary

" Configuration de auto-pairs
let g:AutoPairsShortcutToggle = '<M-p>'

" Configuration de coc.nvim
" Use <tab> and <s-tab> to navigate through popup menu
inoremap <silent><expr> <TAB> pumvisible() ? "\<C-n>" : "\<TAB>"
inoremap <silent><expr> <S-TAB> pumvisible() ? "\<C-p>" : "\<S-TAB>"

" Use <c-space> to trigger completion
inoremap <silent><expr> <C-Space> coc#refresh()

" Configurer les extensions Coc
let g:coc_global_extensions = [
    \ 'coc-tsserver',       " TypeScript/JavaScript language server
    \ 'coc-json',           " JSON language server
    \ 'coc-html',           " HTML language server
    \ 'coc-css',            " CSS language server
    \ 'coc-prettier',       " Prettier for auto-formatting
    \ 'coc-eslint'          " ESLint for linting
    \ ]

" Configurer ShaDa pour éviter les problèmes futurs
set shada='!,'  " Sauvegarder les entrées d'historique et de marque-page seulement

" Commande pour sauvegarder et quitter
nnoremap <leader>w :w<CR>
nnoremap <leader>q :q<CR>

" Autocommandes pour améliorer l'expérience utilisateur
" Ouvrir NERDTree automatiquement au démarrage
autocmd VimEnter * if !argc() | NERDTree | endif
" Fermer Vim si NERDTree est le seul buffer restant
autocmd bufenter * if winnr('$') == 1 && getbufvar(winbufnr(1), '&filetype') ==# 'nerdtree' && argc() == 0 | quit | endif


```

## nvim version

````vim
PS C:\Users\Ranto> nvim --version
NVIM v0.10.0
Build type: Release
LuaJIT 2.1.1713484068
Run "nvim -V1 -v" for more info
PS C:\Users\Ranto>
````

## vim-plug

````vim
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
  https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
````
