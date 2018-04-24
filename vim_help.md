## vim help document

#### normal mode

:h .

:h f

:h *

:h aw

:h s

:h S

:h count

:h ctrl-a

:h ctrl-x

:h operator

:h gU

TimPope's [commentary.vim](https://github.com/tpope/vim-commentary)

:h map-operator

Kana Natsuno's [textobj-entire](https://github.com/kana/vim-textobj-entire)

:h omap-info

Operator-pending-mode

:h g

:h z

:h ctrl-w

#### insertion-mode

:h ctrl-h

:h ctrl-w

:h ctrl-u

:h i_CTRL-[

\<C-o> : switch mode to insertion-normal mode

:h i_CTRL-O

\<C-o>zz

:h i_CTRL-R

\<C-r>{register}

:h i_CTRL-R_CTRL-P

:h i_CTRL-V_digit

:h ga

:h digraphs-default

:h digraph-table

:h v_V

:h visual-repeat

:h gU

:h ex-cmd-index

#### command mode

:[range]delete [x]

:[range]yank [x]

:[line]put [x]

:[range]copy {address}

:[range]move {address}

:[range]join

:[range]normal {command}

:[range]substitute/{pattern}/{string}/[flags]

:[range]global/{pattern}/[cmd]

:h copy

:h move

:h @:

:h quote_:

:h c_CTRL-D

\<C-r>\<C-w>: 将光标下的单词插入到命令行

:h c_CTRL-R_CTRL-W

:h cmdwin

:h:!

:h cmdline-special

:h:shell

\<C-z> and fg

[range]!{filter}



:shell

:!{cmd}

:read !{cmd}

:[range]write !{cmd}

:[range]!{filter}





#### quickfix

:h quickfix

:copen

:cclose

:cnext

:cprev

:cfirst

:clast

:colder

:cnewer

:cnfile

:cpfile

:cc N



#### grep or vimgrep

`vim file +line`  打开file并跳转到第line行(注意file和+之间的空格!)

:h grep

:h grepprg

:h grepformat

:h Ack

