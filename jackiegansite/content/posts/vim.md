---
title: "Vim"
date: 2022-09-11T11:37:58-04:00
draft: false
---

Learning vim(neovim) from the goat himself, [ThePrimeagen](https://www.youtube.com/playlist?list=PLm323Lc7iSW_wuxqmKx_xxNtJC_hJbQ7R).

***Vim As Your Editor (1/6): The Basic Vim Movements*** 
- `j` moving down 
- `k` moving up
- `h` moving left 
- `l` moving right 
- `w` moving forward of a word 
- `b` moving backward of a word 
- "try not to rely on your arrow keys" 
- `yy` yank the line(copy it), store in the register 
- `p` paste the line 
- `dd` delete the line 
- `u` undo the line 
- when you want to delete a function, `dd + dd + dd` isn't practical 
- `shift + v` visual line mode(highlights the line), in this mode you can use `jk` or other commands from above. Like `y,j,k,h,l` and `d` to delete 
- `v` visual word mode(hightlights where you start), in this mode you can use other commands too 
- `i` insert mode, you can type anything. 
- to escape insert mode there is `ctrl + c` or `esc` or `ctrl + [` 
- Usually, your bottom corner shows what mode you're in 
- you can combine vim commands together `d + w` or `d + j` or `d + y` 
- `:w` to save file 
- Practice until you're comfortable with all of these commands