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