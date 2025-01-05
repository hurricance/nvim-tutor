## These are collected from nvim Tutor

### 01
```
h j k l: move
x: delete current character 
i: insert
a: append
```

### 02
```
Operator + Motion
dw: delete word from current position to beginning of the next word, including spaces of tail
de: delete word from current position to the end of this word, excluding spaces of tail
d$: delete all line from current to end

Count + Motion: just move cursor

Operator + Count + Motion: delete as expected
dd: delete a whole line

u: undo the last command
<C-r>(control + r): undo the undos
U: undo all the changes on a line
```

### 03
```
p: past the text in clipboard to next line
P: past the text in clipboard to last line
r: replace the currect character with one you typed
ce: change the word from current position to the end
c + number + motion: change as expected
```

### 04
```
<C-g>: show the filename at the bottom
number + G: go to the typed line
/ + [typed text] + <Enter>: search text, n: next match, N: last match
? + [typed text] + <Enter>: search in backward direction
<C-o>: jump to the last position(in jump list)
<C-i>: go forward
%: type % on any parenthese, will move to the matching one
s: type :s/old/new/g, to replace the whole line old words with new words
%s: type :%s/old/new/g, to replace the whole file old words with new words
```
