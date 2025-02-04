## practical vim

### chapter 01

#### tip 01
```
'.': repeat the last change
line one..
line two.
line three.
line four.
```

#### tip 02
```
don't repeat yourself
two for the piece of one:
C c$
s cl
S ^C
I ^i
A $a
o A<CR>
O ko
```

#### tip 03
```
var foo = "method("+argument1+","+argument2+")";  
to add the space between '+' character, we can simply use "f+, s + <ESC>, ;."
```

#### tip 04
| intent | act | repeat | reverse |
| :-: | :-: | :-: | :-: | 
| make a change | {edit} | . | u |
| scan line for next character | f{char}/t{char} | ; | , |
| scan line for previous character | F{char}/T{char} | ; | , |
| scan document for next match | /pattern<CR> | n | N |
| scan document for previous match | ?pattern<CR> | n | N |
| perform substitution | s/target/replacement | & | u |
| execute a sequence of changes | qx{changes}q | @x | u |

#### tip 05
```
...We're waiting for content before the site can go live...
...If you are content with this, let's go ahead with it...
...We'll launch as soon as we have the content...

if you want to replace 'content' with 'copy' just for the last two lines, just use '/' to search content' and the move to the second 'content', then use 'cw' and type 'copy', type 'n' to find the next one and then use '.' to repeat the last change and so on.
```

#### tip 06
the ideal: one keystroke to move, one keystroke to execute

### chapter 02

#### tip 07
```
before making some changes, think first
in normal mode, we can do many things
```

#### tip 08
```
when you move around useing <Up>, <Down>, <Left>, <Right> in insert mode, the change will be reset
```

#### tip 09
```
compose repeatable changes
choose operation that can be repeatable first
'daw': delete a word
```

#### tip 10 
```
'<C-a>': increase number
'<C-x>': decrease number
if the character of current cursor is not a number, it will look ahead and find the nearest one in current line
number formats: 007 is octal notation, if you don't expect this, use nrformats
```

#### tip 11
```
don't count if you can repeat(granularity)
use a count when it matters
```

#### tip 12
```
operator + motion = action
when an operator command is invoked in duplicate, it acts upon the current line
gUU | gUgU: act upon the current line
```
| trigger | effect |
| :-: | :-: |
| c | change |
| d | delete |
| y | yank into register |
| g~ | swap case |
| gu | make lowercase |
| gU | make uppercase |
| > | shift right |
| < | shift left |
| = | autoindent |
| ! | filter {motion} lines through an external program |

### chapter 03
#### tip 13
```
in insert mode, we can do these:
<C-h>: delete back one charater(backspace)
<C-w>: delete back one word
<C-u>: delete back to start of line
```

#### tip 14
```
get back to normal mode(in insert mode)
<ESC>: switch to normal mode
<C-[>: switch to normal mode
<C-o>: switch to insert normal mode
<C-o>zz: go to insert normal mode then redraws the screen with the current line in the middle of the window
```

#### tip 15
```
in insert mode
<C-r>{register}: paste the text stored in register
<C-r><C-p>{register}: insert text literally and fixed any unintended indentation
```
#### tip 16
```
in insert mode
<C-r>=: open a prompt at the bottom of the screen where we can type the expression that we want to evaluate
```

#### tip 17
```
<C-v>{code}: expects the numeric code to consist of three digits, "A" to '065'; to use unicode, we can use four-digit hexadecimal code by u{code}
ga: we can see the hex, decimal, octal of this character
```
| keystrokes | effect |
| :-: | :-: |
| \<C-v\>{123} | insert character by decimal code |
| \<C-v\>u{123} | insert character by hexadecimal code |
| \<C-v\>{nondigit} | insert nondigit literally |
| \<C-k\>{char1}{char2} | insert character represented by {char1}{char2} digraph |

#### tip 18
```
use ':h digraph-table' to see the usable list
```

#### tip 19
```
gr | gR: virtual replace mode, overwrite characters of screen real estate rather than dealing with the actual character that would eventually be saved in a file  
```

### chapter 04
#### tip 20
```
iw: inner word
<C-g>: toggle between visual and select mode
```

#### tip 21
| command | effect |
| :-: | :-: |
| v | enable character-wise visual mode |
| V | enable line_wise visual mode |
| \<C-v\> | enable block-wise visual mode |
| gv | reselect the last visual selection |
| v / V / \<C-v\> | switch to normal mode from visual mode |
| o | go to other end of highlighted text |

#### tip 22
```
Vj: line-wise visual mode, can select two lines
```

#### tip 23
```
it: text-objects, inner tag block
in visual mode, U/u can toggle case of characters
gUit: toggle current line's it object to uppercase
```

#### tip 24
```
Vr{character}: replace the whole the line with character
```

#### tip 25
```
<C-v>j: to select visual-block of multi lines
```

#### tip 26
```
in block visual-mode, use 'A' or 'I' to enter insert mode for multi lines
'a' and 'i' form the first half of a text object in visual mode 
```

### chapter 05
#### tip 27
| command | effect |
| :-: | :-: |
| [range]delete [x] | delete specified lines [into register x] |
| [range]yank [x] | yank specified lines [into register x] | 
| [range]put [x] | put the text from register x after the specified line |
| [range]copy {address} | copy the specified lines to below the line specified by {address} |
| [range]move {address} | move the specified lines to below the line specified by {address} |
| [range]join | join the specified lines |
| [range]normal {commands} | execute normal mode {commands} on each specified lin |
| [range]substitute/{pattern}/{string}/[flags]| replace occurrences of {pattern} with {string} on each specified line |
| [range]global/{pattern}/[cmd] | execute the ex command [cmd] on all specified lines where the {pattern} matches |
```
ex commands: the commands that we execute from command-line mode
some commands are shared between insert mdoe and command-line mode: <C-w>, <C-u>, <C-v>, <C-k>, <C-r>{register}
```

#### tip 28
```
1. use line numbers as an address
2. specify a range of lines by address
3. specify a range of lines by visual selection
4. specify a range of lines by pattern
5. modify an address using an offset
```
| symbol | address |
| :-: | :-: |
| 1 | first line of the file |
| $ | last line of the file |
| 0 | virtual line above first line of the file |
| . | line where the cursor is placed |
| 'm | line containing mark 'm' |
| '< | start of visual selection |
| '> | end of visual selection |
| % | the entire file (shorthand for :1,$)

#### tip 29
```
t: replace
m: move

```
| command | effect |
| :-: | :-: |
| :6t | copy line 6 to just below the current line |
| :t6 | copy the current line to just below line 6 |
| :t. | duplicate the current line (similar to normal mode yyp)
| :t$ | copy the current line to the end of the file |
| '<,'>t0 | copy the visually selected lines to the start of the file |

#### tip 30
```
{:normal A;}: to insert ';' in current line in command-line mode
use normal to execute normal command in command-line mode
```

#### tip 31
```
use '@:' to repeat the last ex command, after running '@:' for the first time, we can subsequently repeat it with the '@@' command
```

#### tip 32
```
use <C-d> or <Tab> to trigger suggestions, if there are multiple suggestions, use <C-n> or <C-p> to switch suggestions
```

#### tip 33
```
<C-r><C-w>: copies the word under the cursor and inserts it at the command-line prompt
```

#### tip 34
```
{q:}: in normal mode, use this to meet the command-line window, we can see command history in that window
<C-f>: in command-line mode, use this to switch to the command-line window, preserving a copy of the command that was typed at the prompt
```
| command | effect |
| :-: | :-: |
| q/ | open the command-line window with history of searches |
| q: | open the command-line window with history of Ex commands |
| <C-f> | switch from command-line mode to command-line window |

#### tip 35
```
<C-z>: use this to suspends the process that's running vim and returns control to bash, use 'fg' to bring it back
Vim provides a convenient shortcut for setting the range of a :[range]!{filter}
command such as this. The !{motion} operator command drops us into Command-Line mode and prepopulates the [range] with the lines covered by the
specified {motion}
```
| command | effect |
| :-: | :-: |
| :shell | start a shell {return to vim by typing exit} |
| :!{cmd} | execute {cmd} with the shell |
| :read !{cmd} | execute {cmd} in the shell and insert its standard output below the cursor |
| :[range]write !{cmd} | execute {cmd} in the shell with {range} lines as standard input |
| :[range] !{filter} | filter the specified [range] through external program {filter} |

#### tip 36
```
if you need to execute sequence of Ex commands, you can save ourselves work by putting those commands in a script
```