## practical vim

### chapter 01

#### tip1
```
'.': repeat the last change
line one..
line two.
line three.
line four.
```

#### tip2
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

#### tip3
```
var foo = "method("+argument1+","+argument2+")";  
to add the space between '+' character, we can simply use "f+, s + <ESC>, ;."
```

#### tip4
| intent | act | repeat | reverse |
| :-: | :-: | :-: | :-: | 
| make a change | {edit} | . | u |
| scan line for next character | f{char}/t{char} | ; | , |
| scan line for previous character | F{char}/T{char} | ; | , |
| scan document for next match | /pattern<CR> | n | N |
| scan document for previous match | ?pattern<CR> | n | N |
| perform substitution | s/target/replacement | & | u |
| execute a sequence of changes | qx{changes}q | @x | u |

#### tip5
```
...We're waiting for content before the site can go live...
...If you are content with this, let's go ahead with it...
...We'll launch as soon as we have the content...

if you want to replace 'content' with 'copy' just for the last two lines, just use '/' to search content' and the move to the second 'content', then use 'cw' and type 'copy', type 'n' to find the next one and then use '.' to repeat the last change and so on.
```

#### tip6
the ideal: one keystroke to move, one keystroke to execute

### chapter 02

#### tip7
```
before making some changes, think first
in normal mode, we can do many things
```

#### tip8
```
when you move around useing <Up>, <Down>, <Left>, <Right> in insert mode, the change will be reset
```

#### tip9
```
compose repeatable changes
choose operation that can be repeatable first
'daw': delete a word
```

#### tip10
```
'<C-a>': increase number
'<C-x>': decrease number
if the character of current cursor is not a number, it will look ahead and find the nearest one in current line
number formats: 007 is octal notation, if you don't expect this, use nrformats
```

#### tip11
```
don't count if you can repeat(granularity)
use a count when it matters
```

#### tip12
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

#### tip13
```
in insert mode, we can do these:
<C-h>: delete back one charater(backspace)
<C-w>: delete back one word
<C-u>: delete back to start of line
```

#### tip14
```
get back to normal mode(in insert mode)
<ESC>: switch to normal mode
<C-[>: switch to normal mode
<C-o>: switch to insert normal mode
<C-o>zz: go to insert normal mode then redraws the screen with the current line in the middle of the window
```

#### tip15
```
in insert mode
<C-r>{register}: paste the text stored in register
<C-r><C-p>{register}: insert text literally and fixed any unintended indentation
```
#### tip16
```
in insert mode
<C-r>=: open a prompt at the bottom of the screen where we can type the expression that we want to evaluate
```