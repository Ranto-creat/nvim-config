# Installation

## Go to init.vim

``nvim $HOME\AppData\Local\nvim\init.lua``

## Interface vim

```lua
-- Assurer que Packer est installé
local ensure_packer = function()
    local fn = vim.fn
    local install_path = fn.stdpath('data')..'/site/pack/packer/start/packer.nvim'
    if fn.empty(fn.glob(install_path)) > 0 then
        fn.system({
            'git',
            'clone',
            '--depth', '1',
            'https://github.com/wbthomason/packer.nvim',
            install_path
        })
        vim.cmd [[packadd packer.nvim]]
    end
end

ensure_packer()

local function setup_theme()
    vim.opt.background = 'dark'
    vim.cmd('colorscheme gruvbox')
end

require('packer').startup(function(use)
    -- Packer peut se mettre à jour
    use 'wbthomason/packer.nvim'

    -- Thème Gruvbox
    use 'gruvbox-community/gruvbox'

    -- Vim-airline et ses thèmes
    use 'vim-airline/vim-airline'
    use 'vim-airline/vim-airline-themes'

    -- LSP, autocomplétion et snippets
    use 'neovim/nvim-lspconfig'
    use 'hrsh7th/nvim-cmp'
    use 'hrsh7th/cmp-nvim-lsp'
    use 'hrsh7th/cmp-buffer'
    use 'hrsh7th/cmp-path'
    use 'saadparwaiz1/cmp_luasnip'
    use 'L3MON4D3/LuaSnip'

    -- Interface utilisateur
    use 'itchyny/lightline.vim'
    -- use 'kyazdani42/nvim-web-devicons'
    use 'ryanoasis/vim-devicons'
    use 'preservim/nerdtree'
    use 'easymotion/vim-easymotion'
    use 'jiangmiao/auto-pairs'
    use 'tpope/vim-commentary'
    use 'junegunn/fzf'
    use 'junegunn/fzf.vim'
    use 'Yggdroot/indentLine'

    -- Intégration Git
    use 'tpope/vim-fugitive'

    -- Plugins pour les langages spécifiques
    use 'hail2u/vim-css3-syntax'
    use 'cakebaker/scss-syntax.vim'
    use 'othree/html5.vim'
    use 'mattn/emmet-vim'
    use {
        'prettier/vim-prettier',
        run = 'yarn install --frozen-lockfile --production',
        branch = 'release/0.x'
    }
    use 'dense-analysis/ale'
    use 'ap/vim-css-color'
    use 'norcalli/nvim-colorizer.lua'
    use 'maxmellon/vim-jsx-pretty'
    use 'pangloss/vim-javascript'
    use {'styled-components/vim-styled-components', branch = 'main'}

    -- Plugins pour Markdown
    use 'plasticboy/vim-markdown'
    use 'godlygeek/tabular'
    use {
        'iamcco/markdown-preview.nvim',
        run = 'cd app && yarn install'
    }

    -- COC pour l'autocomplétion
    use {'neoclide/coc.nvim', branch = 'release'}

    if packer_bootstrap then
        require('packer').sync()
    end
end)

-- Appeler setup_theme après avoir installé tous les plugins
vim.cmd [[autocmd User PackerComplete ++once lua setup_theme()]]



-- Activer la numérotation des lignes
vim.opt.number = true
vim.opt.relativenumber = true

-- Activer la coloration syntaxique
vim.cmd('syntax on')

-- Activer les couleurs 24 bits  
vim.opt.termguicolors = true  

-- Charger le thème Gruvbox  
vim.cmd[[colorscheme gruvbox]]  

-- Couleurs vives pour un meilleur contraste  
vim.api.nvim_set_hl(0, "Normal", {fg="#EAEAEA", bg="#1E1E1E"})  
vim.api.nvim_set_hl(0, "Comment", {fg="#A6A6A6", bg="NONE", italic=true})  
vim.api.nvim_set_hl(0, "Identifier", {fg="#FF79C6", bg="NONE"})  
vim.api.nvim_set_hl(0, "Statement", {fg="#FFB86C", bg="NONE"})  
vim.api.nvim_set_hl(0, "PreProc", {fg="#8BE9FD", bg="NONE"})  
vim.api.nvim_set_hl(0, "Type", {fg="#50FA7B", bg="NONE"})  
vim.api.nvim_set_hl(0, "Constant", {fg="#BD93F9", bg="NONE"})  
vim.api.nvim_set_hl(0, "Conditional", {fg="#FF5555", bg="NONE"})  
vim.api.nvim_set_hl(0, "Error", {fg="#FF5555", bg="NONE"})  
vim.api.nvim_set_hl(0, "CursorLine", {bg="#44475A"})  
vim.api.nvim_set_hl(0, "LineNr", {fg="#6272A4", bg="NONE"})

-- Configurer vim-airline
vim.g.airline_theme = 'gruvbox'
vim.g.airline_powerline_fonts = 1
vim.g['airline#extensions#tabline#enabled'] = 1
vim.g['airline#extensions#tabline#formatter'] = 'default'

-- Configurer NERDTree
vim.api.nvim_set_keymap('n', '<C-n>', ':NERDTreeToggle<CR>', { noremap = true, silent = true })
vim.g.NERDTreeShowHidden = 1
vim.g.NERDTreeMinimalUI = 1
vim.g.NERDTreeDirArrowExpandable = '+'
vim.g.NERDTreeDirArrowCollapsible = '~'
vim.cmd([[
autocmd VimEnter * NERDTree
autocmd BufEnter * if tabpagenr('$') == 1 && bufname() == '' && len(filter(range(1, bufnr('$')), 'buflisted(v:val)')) == 1 | q | endif
]])

-- Activer les lignes d'entrelacement
vim.opt.cursorline = true

-- Configurer les onglets et les espaces
vim.opt.tabstop = 4
vim.opt.shiftwidth = 4
vim.opt.expandtab = true

-- Activer les caractères invisibles
vim.opt.list = true
vim.opt.listchars = { tab = '▸\\ ', trail = '·', extends = '>', precedes = '<', nbsp = '·' }

-- Augmenter la taille du tampon de défilement
vim.opt.scrolloff = 8

-- Utiliser les diviseurs verticaux pour les splits
vim.opt.splitright = true
vim.opt.splitbelow = true

-- Mettre en évidence la recherche
vim.opt.hlsearch = true
vim.opt.incsearch = true

-- Activer le copier-coller avec le système
vim.opt.clipboard = 'unnamedplus'

-- Configuration de Gruvbox
vim.g.gruvbox_contrast_dark = 'hard'
vim.g.gruvbox_invert_selection = 0

-- Configuration de la barre d'état lightline
--vim.g.lightline = {
--    colorscheme = 'gruvbox',
--    active = {
--        left = { { 'mode', 'paste' }, { 'readonly', 'filename', 'modified' } }
--    },
--    component_function = {
--        filename = 'LightlineFilename'
--    }
--}

function LightlineFilename()
  return vim.fn.expand('%:t') == '' and '[No Name]' or vim.fn.expand('%:t')
end

-- Configurer indentLine
vim.g.indentLine_char = '▏'

-- Configuration de EasyMotion
vim.api.nvim_set_keymap('n', '<Leader><Leader>w', '<Plug>(easymotion-overwin-w)', {})

-- Configuration de vim-commentary
vim.api.nvim_set_keymap('n', 'gc', '<Plug>Commentary', {})
vim.api.nvim_set_keymap('v', 'gc', '<Plug>Commentary', {})

-- Configuration de auto-pairs
vim.g.AutoPairsShortcutToggle = '<M-p>'

-- Configuration de coc.nvim
vim.api.nvim_set_keymap('i', '<TAB>', 'pumvisible() ? "\\<C-n>" : "\\<TAB>"', { noremap = true, expr = true, silent = true })
vim.api.nvim_set_keymap('i', '<S-TAB>', 'pumvisible() ? "\\<C-p>" : "\\<S-TAB>"', { noremap = true, expr = true, silent = true })
vim.api.nvim_set_keymap('i', '<C-Space>', 'coc#refresh()', { noremap = true, expr = true, silent = true })

-- Extensions supplémentaires pour Coc
vim.g.coc_global_extensions = {
    'coc-css',
    'coc-html',
    'coc-stylelintplus',
    'coc-prettier',
    'coc-tsserver',
    'coc-eslint',
    'coc-markdownlint',
    'coc-emmet',
}

-- Configurer ShaDa pour éviter les problèmes futurs
vim.opt.shada = "'100,<50,s10,h"

-- Configurer vim-css3-syntax
vim.g.css3_syntax_sass = 1

-- Configurer vim-prettier
vim.g['prettier#autoformat'] = 1
vim.g['prettier#autoformat_require_pragma'] = 0
vim.g['prettier#config#config_precedence'] = 'prefer-file'

-- Configurer ALE (Asynchronous Lint Engine)
vim.g.ale_linters = {
    javascript = {'eslint'},
    javascriptreact = {'eslint'},
    typescript = {'eslint', 'tsserver'},
    typescriptreact = {'eslint', 'tsserver'},
    css = {'stylelint'},
    scss = {'stylelint'},
    html = {'tidy'}
}
vim.g.ale_fixers = {
    javascript = {'prettier', 'eslint'},
    javascriptreact = {'prettier', 'eslint'},
    typescript = {'prettier', 'eslint'},
    typescriptreact = {'prettier', 'eslint'},
    css = {'prettier', 'stylelint'},
    scss = {'prettier', 'stylelint'},
    html = {'prettier', 'tidy'}
}
vim.g.ale_fix_on_save = 1

-- Configurer Emmet
vim.g.user_emmet_leader_key = '<C-Z>'
vim.cmd([[
autocmd FileType html,css,scss,jsx,tsx EmmetInstall
]])

-- Configurer vim-css-color
vim.g.css_color_vim_do_not_rename_syntax_groups = 1

-- Configurer nvim-colorizer
require('colorizer').setup()

-- Autres configurations possibles
vim.cmd('set lazyredraw')
vim.cmd('set updatetime=300')
vim.opt.scrolloff = 8
vim.opt.relativenumber = true
vim.opt.splitright = true
vim.opt.splitbelow = true
vim.opt.laststatus = 2
vim.opt.showmode = false

-- Ajuster les couleurs des diagnostics de CoC
vim.cmd('highlight CocDiagnosticError guifg=#fb4934 gui=underline')
vim.cmd('highlight CocDiagnosticWarning guifg=#fabd2f gui=underline')
vim.cmd('highlight CocDiagnosticInfo guifg=#83a598 gui=underline')
vim.cmd('highlight CocDiagnosticHint guifg=#8ec07c gui=underline')

-- Configuration pour le panneau de sortie des messages CoC
vim.g.coc_config_home = '~/.config/nvim/coc-settings.json'

-- augmentation de time out
vim.cmd('let g:packer_max_jobs = 10')

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
