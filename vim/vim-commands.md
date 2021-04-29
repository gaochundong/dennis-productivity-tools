# vim启动

```bash
在命令行窗口中输入以下命令即可
vim 直接启动vim
vim filename 打开vim并创建名为filename的文件
```

# vim模式

```bash
正常模式（按Esc或Ctrl+[进入） 左下角显示文件名或为空
插入模式（按i键进入） 左下角显示--INSERT--
可视模式（不） 左下角显示--VISUAL--
导航命令
```

# 命令历史

```bash
以:和/开头的命令都有历史纪录，可以首先键入:或/然后按上下箭头来选择某个历史命令。
```

# 文件命令

```bash
打开单个文件    vim file
同时打开多个文件    vim file1 file2 file3 ...
在vim窗口中打开一个新文件   :open file
在新窗口中打开文件  :split file
切换到下一个文件    :bn
切换到上一个文件    :bp
```

# 移动命令

```bash
^:移动光标到行首；
$:移动光标到行尾；
ctrl-b:类似于键盘上的"PgUp"(b为backword)
ctrl-f：类似于键盘上的"PgDn"(f为forword)
G：移动到末行；
1G：移动到首行；
50G：移动到50行；
H：移动到当前窗口的首行；
M：移动到当前窗口的中间位置；
L：移动光标到当前窗口的最后一行；
w:光标移动到下一个单词的词首；注：对于中文，连续的多个汉字作为一个word。
2w:重复执行w操作2次；
e:光标移动到下一个单词的词尾；
5e:重复执行e操作5次；
b：向前移动光标，移动到前一个单词的词首；

h 左移一个字符
l 右移一个字符，这个命令很少用，一般用w代替。
k 上移一个字符
j 下移一个字符
w 向前移动一个单词（光标停在单词首部），如果已到行尾，则转至下一行行首。此命令快，可以代替l命令。
b 向后移动一个单词 2b 向后移动2个单词
e，同w，只不过是光标停在单词尾部
ge，同b，光标停在单词尾部。
^ 移动到本行第一个非空白字符上。
0（数字0）移动到本行第一个字符上，
<HOME> 移动到本行第一个字符。同0健。
$ 移动到行尾 3$ 移动到下面3行的行尾
gg 移动到文件头。 = [[
G（shift + g） 移动到文件尾。 = ]]
f（find）命令也可以用于移动，fx将找到光标后第一个为x的字符，3fd将找到第三个为d的字符。
F 同f，反向查找。
跳到指定行，:n，回车，比如跳到240行就是 :240回车。另一个方法是行号+G，比如230G跳到230行。
Ctrl + e 向下滚动一行
Ctrl + y 向上滚动一行
Ctrl + d 向下滚动半屏
Ctrl + u 向上滚动半屏
Ctrl + f 向下滚动一屏
Ctrl + b 向上滚动一屏
```

# 句子(sentences)直接移动操作

```bash
):光标移动到下一句；
(:光标移动到上一句；
3):光标移动到向下3句
```

# 段落(paragraphs)直接移动操作

```bash
{:向上移动一个段落；
}:向下移动一个段落
3}:向下移动3个段落
```

# vim快速选中并复制粘贴替换一个单词

```bash
光标移动到aaa的开头，按 v 按e 按y
光标移动到bbb的开头，按 v 按e 按p
也就说，快速选中一个单词，按v按e即可。
复制一个单词: yaw
复制一行: yim 光标在中间
```

# 插入命令

```bash
i 在当前位置生前插入
I 在当前行首插入
a 在当前位置后插入
A 在当前行尾插入
o 在当前行之后插入一行
O 在当前行之前插入一行
```

# 查找命令

```bash
/text　　查找text，按n健查找下一个，按N健查找前一个。
?text　　查找text，反向查找，按n健查找下一个，按N健查找前一个。
vim中有一些特殊字符在查找时需要转义　　.*[]^%/?~$
:set ignorecase　　忽略大小写的查找
:set noignorecase　　不忽略大小写的查找
:set hlsearch　　高亮搜索结果，所有结果都高亮显示，而不是只显示一个匹配。
:set nohlsearch　　关闭高亮搜索显示
:nohlsearch　　关闭当前的高亮显示，如果再次搜索或者按下n或N键，则会再次高亮。
:set incsearch　　逐步搜索模式，对当前键入的字符进行搜索而不必等待键入完成。
:set wrapscan　　重新搜索，在搜索到文件头或尾时，返回继续搜索，默认开启。
```

# 替换命令

```bash
ra 将当前字符替换为a，当期字符即光标所在字符。
s/old/new/ 用old替换new，替换当前行的第一个匹配
s/old/new/g 用old替换new，替换当前行的所有匹配
%s/old/new/ 用old替换new，替换所有行的第一个匹配
%s/old/new/g 用old替换new，替换整个文件的所有匹配
:10,20 s/^/ /g 在第10行知第20行每行前面加四个空格，用于缩进。
ddp 交换光标所在行和其下紧邻的一行。
```

# 撤销和重做

```bash
u 撤销（Undo）
U 撤销对整行的操作
Ctrl + r 重做（Redo），即撤销的撤销。
```

# 删除命令

```bash
x 删除当前字符
3x 删除当前光标开始向后三个字符
X 删除当前字符的前一个字符。X=dh
dl 删除当前字符， dl=x
dh 删除前一个字符
dd 删除当前行
dj 删除上一行
dk 删除下一行
10d 删除当前行开始的10行。
D 删除当前字符至行尾。D=d$
d$ 删除当前字符之后的所有字符（本行）
kdgg 删除当前行之前所有行（不包括当前行）
jdG（jd shift + g） 删除当前行之后所有行（不包括当前行）
:1,10d 删除1-10行
:11,$d 删除11行及以后所有的行
:1,$d 删除所有行
J 删除两行之间的空行，实际上是合并两行。
```

# 拷贝和粘贴

```bash
yy 拷贝当前行
nyy 拷贝当前后开始的n行，比如2yy拷贝当前行及其下一行。
p 在当前光标后粘贴,如果之前使用了yy命令来复制一行，那么就在当前行的下一行粘贴。
shift+p 在当前行前粘贴
:1,10 co 20 将1-10行插入到第20行之后。
:1,$ co $ 将整个文件复制一份并添加到文件尾部。
正常模式下按v（逐字）或V（逐行）进入可视模式，然后用jklh命令移动即可选择某些行或字符，再按y即可复制
ddp交换当前行和其下一行
xp交换当前字符和其后一个字符
```

# 剪切命令

```bash
正常模式下按v（逐字）或V（逐行）进入可视模式，然后用jklh命令移动即可选择某些行或字符，再按d即可剪切
ndd 剪切当前行之后的n行。利用p命令可以对剪切的内容进行粘贴
:1,10d 将1-10行剪切。利用p命令可将剪切后的内容进行粘贴。
:1, 10 m 20 将第1-10行移动到第20行之后。
```

# 退出命令

```bash
:wq 保存并退出
ZZ 保存并退出
:q! 强制退出并忽略所有更改
:e! 放弃所有修改，并打开原来文件。
```

# 窗口命令

```bash
:split或:new 打开一个新窗口，光标停在顶层的窗口上
:split file或:new file 用新窗口打开文件
split打开的窗口都是横向的，使用vsplit可以纵向打开窗口。
Ctrl+ww 移动到下一个窗口
Ctrl+wj 移动到下方的窗口
Ctrl+wk 移动到上方的窗口
```

# 关闭窗口

```bash
:close 最后一个窗口不能使用此命令，可以防止意外退出vim。
:q 如果是最后一个被关闭的窗口，那么将退出vim。
ZZ 保存并退出。
关闭所有窗口，只保留当前窗口:only
```

# 注释命令

```bash
3,5 s/^/#/g 注释第3-5行
3,5 s/^#//g 解除3-5行的注释
1,$ s/^/#/g 注释整个文档。
:%s/^/#/g 注释整个文档，此法更快。
```

# 帮助命令

```bash
:help or F1 显示整个帮助
:help xxx 显示xxx的帮助，比如 :help i, :help CTRL-[（即Ctrl+[的帮助）。
:help 'number' Vim选项的帮助用单引号括起
:help <Esc> 特殊键的帮助用<>扩起
:help -t Vim启动参数的帮助用-
：help i_<Esc> 插入模式下Esc的帮助，某个模式下的帮助用模式_主题的模式
帮助文件中位于||之间的内容是超链接，可以用Ctrl+]进入链接，Ctrl+o（Ctrl + t）返回
其他非编辑命令
```