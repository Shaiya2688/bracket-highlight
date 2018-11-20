Install:
--------

### via Vundle:

```vim
Plugin 'Shaiya2688/bracket-highlight'
let g:rainbow_active = 1 "0 if you want to enable it later via :RainbowToggle
```

### Manually:

- first, execute the following commands (for windows users, use `~/vimfiles` instead of `~/.vim`)

	```sh
	git clone https://github.com/Shaiya2688/bracket-highlight.git
	cd bracket-highlight 
	cp plugin/* ~/.vim/plugin
	cp autoload/* ~/.vim/autoload
	```

- second, add the follow sentences to your `.vimrc` or `_vimrc` :

	```vim
	let g:rainbow_active = 1 "0 if you want to enable it later via :RainbowToggle
	```

- third, restart your vim and enjoy coding.

Configure:
----------

There is an example for advanced configuration (which I'm using), add it to your vimrc and edit it as you wish (just keep the format).

```vim
let g:rainbow_active = 0 "command is :RainbowToggle
map \5 :RainbowToggle<cr>
let g:rainbow_conf = {
	\	'cterms': ['NONE', 'NONE', 'NONE', 'NONE', 'NONE', 'bold', 'bold', 'bold', 'bold', 'bold'],
	\	'ctermbgs': ['6', '2', '3', '1', '5', '4', '7', '1', '2', '6'],
	\	'ctermfgs': ['0', '0', '0', '0', '0', '7', '3', '7', '3', '7'],
	\	'guibgs': ['#8CCBEA', '#A4E57E', '#FFDB72', '#FF7272', '#FFB3FF', '#9999FF', '#9999FF', '#9999FF', '#9999FF', '#9999FF'],
	\	'guifgs': ['black', 'black', 'black', 'black', 'black', 'black', 'black', 'black', 'black', 'black'],
	\	'operators': '',
	\	'parentheses': ['start=/(/ end=/)/ fold', 'start=/\[/ end=/\]/ fold', 'start=/{/ end=/}/ fold'],
	\	'separately': {
	\		'*': {},
	\		'tex': {
	\			'parentheses': ['start=/(/ end=/)/', 'start=/\[/ end=/\]/'],
	\		},
	\		'lisp': {
	\			'guifgs': ['royalblue3', 'darkorange3', 'seagreen3', 'firebrick', 'darkorchid3'],
	\		},
	\		'vim': {
	\			'parentheses': ['start=/(/ end=/)/', 'start=/\[/ end=/\]/', 'start=/{/ end=/}/ fold', 'start=/(/ end=/)/ containedin=vimFuncBody', 'start=/\[/ end=/\]/ containedin=vimFuncBody', 'start=/{/ end=/}/ fold containedin=vimFuncBody'],
	\		},
	\		'html': {
	\			'parentheses': ['start=/\v\<((area|base|br|col|embed|hr|img|input|keygen|link|menuitem|meta|param|source|track|wbr)[ >])@!\z([-_:a-zA-Z0-9]+)(\s+[-_:a-zA-Z0-9]+(\=("[^"]*"|'."'".'[^'."'".']*'."'".'|[^ '."'".'"><=`]*))?)*\>/ end=#</\z1># fold'],
	\		},
	\		'css': 0,
	\	}
	\}
```

- 'cterm': highlight arguments for color terminals.
- 'ctermbgs': colors for terms.
- 'ctermfgs': colors for terms.
- 'guibgs': colors for gui interface, will be used in order.
- 'guifgs': colors for gui interface, will be used in order.
- 'operators': describe the operators you want to highlight (note: be careful about special characters which needs escaping, you can find more examples [here](https://github.com/luochen1990/rainbow/issues/3), and you can also read the [vim help about syn-pattern](http://vimdoc.sourceforge.net/htmldoc/syntax.html#:syn-pattern)).
- 'parentheses': describe what will be processed as parentheses, a pair of parentheses was described by two re pattern.
- 'separately': configure for specific filetypes (decided by &ft), key `*` for filetypes without separate configuration, value `0` means disable rainbow only for this type of files, value `"default"` means keep the default shim for this filetype (notice: the default shim config will change between plugin version).
- keep a field empty to use the default setting.

User Command:
-------------

- **:RainbowToggle**		--you can use it to toggle this plugin.

------------------------------------------------------------------
