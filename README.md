# breeze.vim

**v1.0**

HTML navigation inspired by vim-easymotion.

**Features:**
* HTML navigation like vim-easymotion.
* Tag matching.
* Current element highlighting.
* Low level DOM navigation.

### Requirements
* Vim compiled with python 2.6+


### Installation
You can either extract the content of the folder into the `$HOME/.vim`
directory or use plugin managers such as Vundle or Pathogen.



## Tag jumping
![Screenshot](extra/jump.gif "Tag jumping inspired by vim-easymotion")   

As you can see this form is heavily inspired by vim-easimotion.
To jump to following tags use the command `BreezeJumpForward`. 
Use `BreezeJumpBackward` to move to preceding tags.

When you fire one of the aforementioned commands, Breeze display
colored marks on the tags you can jump to and wait for your choice.
Once you have moved to a tag you can easily jump back using the `CTRL+O` 
vim mapping (:help CTRL+O). Note that when you are asked to insert the target
key you can exit the whole process pressing either `<ESC>` or `CTRL+C`.

### Settings

**NOTE**: when setting the following options you can follow two ways:

  * use a long list of "attribute=color .." (as you would normally do when
     defining highlight groups) such as guifg=#424242, ctermfg=242, etc..

  * use the name of a previously defined highlight group. Note, however,
     that this does not work with highlight groups defined in your `.vimrc`.


**g:breeze_shade_color**: this setting defines the color that is used to shade
the background text when you are using the *jumping* functionality.
    
default: `gui=NONE guifg=#777777 cterm=NONE ctermfg=242`


**g:breeze_shade_color_darkbg**: this setting defines the color that is used to
shade the background text when you are using the *jumping* functionality with
dark backgrounds (&background == dark). By default the value is equal to the
*g:breeze_shade_color* setting.
    
default: `gui=NONE guifg=#777777 cterm=NONE ctermfg=242`


**g:breeze_jumpmark_color**: this setting defines the color that is used to
highlight jump marks when you are using the *jumping* functionality.
   
default: `gui=bold guifg=#ff6155 cterm=bold ctermfg=203`


**g:breeze_jumpmark_color_darkbg**: this setting defines the color that is used
to highlight jump marks when you are using the *jumping* functionality with
dark backgrounds (&background == dark). By default the value is equal to the 
*g:breeze_jumpmark_color* setting.
   
default: `gui=bold guifg=#ff6155 cterm=bold ctermfg=203`



## Tag matching and current element highlighting
![Screenshot](extra/high.gif "Current element highlighting")   

By default Breeze highlights the opening and closing tags of the current element.
To turn off this functionality you can set `g:breeze_highlight_element` to 0. However,
you always have at your disposal the `BreezeHlElement` command to highlight the current element.
If you prefer highlighting the whole element as a block you can use the `BreezeHlElementBlock` command
(just like the `vat` vim motion. However it seems not working properly with self enclosing tags).

Another useful command is `BreezeMatchTag`. If the cursor is on an opening tag,
this command moves the cursor to the corresponding closing tag, and vice-versa.
If the command is called in within a element, this command moves the cursor to
its opening tag. Remember that you can easily jump back to the original position
pressing `CTRL+O`.


### Settings

**NOTE**: when defining the following settings you have two options:

  * use a long list of "attribute=color .." (as you would normally do when
     defining highlight groups) such as guifg=#424242, ctermfg=242, etc..

  * use the name of a previously defined highlight group. Note, however,
     that this does not work with highlight groups defined in your `.vimrc`.


**g:breeze_highlight_tag**: set this setting to 0 to disable automatic highlighting
of the opening and closing tags of the current element.
  
default: `1`


**g:breeze_tag_color**: this setting defines the color that is used to
highlight opening and closing tags.
   
default: `MatchParen`


**g:breeze_tag_color_darkbg**: this setting defines the color that is used to
highlight opening and closing tags with dark backgrounds (&background == dark).
By default the value is equal to the *g:breeze_tag_color* setting.
   
default: `MatchParen`


**g:breeze_tagblock_color**: this setting defines the color that is used to
highlight the current element as a block.
   
default: `MatchParen`


**g:breeze_tagblock_color_darkbg**: this setting defines the color that is used to
highlight the current element as a block with dark backgrounds (&background == dark).
By default the value is equal to the *g:breeze_tagblock_color* setting.
  
default: `MatchParen`



## DOM navigation
![Screenshot](extra/dom.gif "DOM navigation")   

The available commands for DOM navigation cover only low level movements at the
moment but they are going to be expanded in the future.


### Commands

**BreezeNextSibling**
Moves the cursor to the next sibling node.

**BreezePrevSibling**
Moves the cursor to the previous sibling node.

**BreezeFirstChild**
Moves the cursor to the first child node.

**BreezeLastChild**
Moves the cursor to the last child node.

**BreezeParent**
Moves the cursor to the parent node.
