# vim命令速查表

> 个人vim命令速查表。

[vim-cheatsheet](https://github.com/chloneda/vim-cheatsheet) | [Vim官网](https://www.vim.org/) | [Github](https://github.com/vim/vim)



## 光标移动

```bash
h                   # 光标左移，同 <Left> 键
j                   # 光标下移，同 <Down> 键
k                   # 光标上移，同 <Up> 键
l                   # 光标右移，同 <Right> 键
Ctrl+f              # 下一页 --> move forward one full screen
Ctrl+b              # 上一页 --> move back one full screen
Ctrl+u              # 上移半屏 --> move up 1/2 a screen
Ctrl+d              # 下移半屏 --> move down 1/2 a screen
0                   # 跳到行首（是数字零，不是字母O），效用等同于 <Home> 键
^                   # 跳到从行首开始第一个非空白字符
$                   # 跳到行尾，效用等同于 <End> 键
gg                  # 跳到第一行，效用等同于 Ctrl+<Home>
G                   # 跳到最后一行，效用等同于 Ctrl+<End>
nG                  # 跳到第n行，比如 10G 是移动到第十行
:n                  # 跳到第n行，比如 :10<回车> 是移动到第十行
10%                 # 移动到文件 10% 处
15|                 # 移动到当前行的 15列
w                   # 跳到下一个单词开头 (word: 标点或空格分隔的单词)
W                   # 跳到下一个单词开头 (WORD: 空格分隔的单词)
e                   # 跳到下一个单词尾部 (word: 标点或空格分隔的单词)
E                   # 跳到下一个单词尾部 (WORD: 空格分隔的单词)
b                   # 上一个单词头 (word: 标点或空格分隔的单词)
B                   # 上一个单词头 (WORD: 空格分隔的单词)
ge                  # 上一个单词尾
)                   # 向前移动一个句子（句号分隔）
(                   # 向后移动一个句子（句号分隔）
}                   # 向前移动一个段落（空行分隔）
{                   # 向后移动一个段落（空行分隔）
<enter>             # 移动到下一行首个非空字符
+                   # 移动到下一行首个非空字符（同回车键）
-                   # 移动到上一行首个非空字符
H                   # 移动到屏幕上部
M                   # 移动到屏幕中部
L                   # 移动到屏幕下部
fx                  # 跳转到下一个为 x 的字符，2f/ 可以找到第二个斜杆
Fx                  # 跳转到上一个为 x 的字符
tx                  # 跳转到下一个为 x 的字符前
Tx                  # 跳转到上一个为 x 的字符前
;                   # 跳到下一个 f/t 搜索的结果
,                   # 跳到上一个 f/t 搜索的结果
<S-Left>            # 按住 SHIFT 按左键，向左移动一个单词
<S-Right>           # 按住 SHIFT 按右键，向右移动一个单词
<S-Up>              # 按住 SHIFT 按上键，向上翻页
<S-Down>            # 按住 SHIFT 按下键，向下翻页
gm                  # 移动到行中
gj                  # 光标下移一行（忽略自动换行）
gk                  # 光标上移一行（忽略自动换行）
```



## 插入模式

```bash
i                   # 在光标处进入插入模式
I                   # 在行首进入插入模式
a                   # 在光标后进入插入模式
A                   # 在行尾进入插入模式
o                   # 在下一行插入新行并进入插入模式
O                   # 在上一行插入新行并进入插入模式
gi                  # 进入到上一次插入模式的位置
<esc>               # 退出插入模式
Ctrl-[              # 退出插入模式（等价于 ESC）
```



## 插入模式

**注：由 i, I, a, A, o, O 等命令进入插入模式**

```bash
<Up>                # 光标向上移动
<Down>              # 光标向下移动
<Left>              # 光标向左移动
<Right>             # 光标向右移动
<S-Left>            # 按住 SHIFT 按左键，向左移动一个单词
<S-Right>           # 按住 SHIFT 按右键，向右移动一个单词
<S-Up>              # 按住 SHIFT 按上键，向上翻页
<S-Down>            # 按住 SHIFT 按下键，向下翻页
<PageUp>            # 上翻页
<PageDown>          # 下翻页
<Delete>            # 删除光标处字符
<BS>                # Backspace 向后删除字符
<Home>              # 光标跳转行首
<End>               # 光标跳转行尾
Ctrl-W              # 向后删除单词
Ctrl-O              # 临时退出插入模式，执行单条命令又返回插入模式
Ctrl-\ Ctrl-O       # 临时退出插入模式（光标保持），执行单条命令又返回插入模式
Ctrl-R 0            # 插入寄存器（内部 0号剪贴板）内容，Ctrl-R 后可跟寄存器名
Ctrl-R "            # 插入匿名寄存器内容，相当于插入模式下 p粘贴
Ctrl-R =            # 插入表达式计算结果，等号后面跟表达式
Ctrl-R :            # 插入上一次命令行命令
Ctrl-R /            # 插入上一次搜索的关键字
Ctrl-F              # 自动缩进
Ctrl-U              # 删除当前行所有字符
Ctrl-V {char}       # 插入非数字的字面量
Ctrl-V {number}     # 插入三个数字代表的 ascii/unicode 字符
Ctrl-V 065          # 插入 10进制 ascii 字符（两数字） 065 即 A字符
Ctrl-V x41          # 插入 16进制 ascii 字符（三数字） x41 即 A字符
Ctrl-V o101         # 插入  8进制 ascii 字符（三数字） o101 即 A字符
Ctrl-V u1234        # 插入 16进制 unicode 字符（四数字）
Ctrl-V U12345678    # 插入 16进制 unicode 字符（八数字）
Ctrl-K {ch1} {ch2}  # 插入 digraph（见 :h digraph），快速输入日文或符号等
```



## 文本编辑

```bash
r                   # 替换当前字符
R                   # 进入替换模式，直至 ESC 离开
s                   # 替换字符（删除光标处字符，并进入插入模式，前可接数量）
S                   # 替换行（删除当前行，并进入插入模式，前可接数量）
cc                  # 改写当前行（删除当前行并进入插入模式），同 S
cw                  # 改写光标开始处的当前单词
ciw                 # 改写光标所处的单词
caw                 # 改写光标所处的单词，并且包括前后空格（如果有的话）
c0                  # 改写到行首
c^                  # 改写到行首（第一个非零字符）
c$                  # 改写到行末
C                   # 改写到行尾（同c$）
ci"                 # 改写双引号中的内容
ci'                 # 改写单引号中的内容
cib                 # 改写小括号中的内容
cab                 # 改写小括号中的内容（包含小括号本身）
ci)                 # 改写小括号中的内容
ci]                 # 改写中括号中内容
ciB                 # 改写大括号中内容
caB                 # 改写大括号中的内容（包含大括号本身）
ci}                 # 改写大括号中内容
cit                 # 改写 xml tag 中的内容
cis                 # 改写当前句子
c2w                 # 改写下两个单词
ct(                 # 改写到小括号前
x                   # 删除当前字符，前面可以接数字，3x代表删除三个字符
X                   # 向前删除字符
dd                  # 删除(剪切)当前行 --> delete (cut) a line 
d0                  # 删除(剪切)到行首
d^                  # 删除(剪切)到行首（第一个非零字符）
d$                  # 删除(剪切)到行末
D                   # 删除(剪切)到行末（同 d$）
dw                  # 删除(剪切)当前单词
diw                 # 删除(剪切)光标所处的单词
daw                 # 删除(剪切)光标所处的单词，并包含前后空格（如果有的话）
di"                 # 删除双引号中的内容
di'                 # 删除单引号中的内容
dib                 # 删除小括号中的内容
di)                 # 删除小括号中的内容
dab                 # 删除小括号内的内容（包含小括号本身）
di]                 # 删除中括号中内容
diB                 # 删除大括号中内容
di}                 # 删除大括号中内容
daB                 # 删除大括号内的内容（包含大括号本身）
dit                 # 删除 xml tag 中的内容
dis                 # 删除当前句子
d2w                 # 删除下两个单词
dt(                 # 删除到小括号前
dgg                 # 删除到文件头部
dG                  # 删除到文件尾部
d}                  # 删除下一段
d{                  # 删除上一段
u                   # 撤销
U                   # 撤销整行操作
Ctrl-R              # 撤销上一次 u 命令
J                   # 链接多行为一行
.                   # 重复上一次操作
~                   # 替换大小写
g~iw                # 替换当前单词的大小写
gUiw                # 将单词转成大写
guiw                # 将当前单词转成小写
guu                 # 全行转为小写
gUU                 # 全行转为大写
<<                  # 减少缩进
>>                  # 增加缩进
==                  # 自动缩进
Ctrl-A              # 增加数字
Ctrl-X              # 减少数字
:Ctrl+p             # 插入模式下文字自动补全
```



## 复制粘贴

```bash
:m+1                # 下移1行
:m-2                # 上移1行
p                   # 粘贴到光标后
P                   # 粘贴到光标前
v                   # 开始标记
y                   # 复制标记内容
V                   # 开始按行标记
Ctrl-V              # 开始列标记
y$                  # 复制当前位置到本行结束的内容
yy                  # 复制当前行 --> yank (copy) a line
Y                   # 复制当前行，同 yy
yiw                 # 复制当前单词
3yy                 # 复制光标下三行内容
v0                  # 选中当前位置到行首
v$                  # 选中当前位置到行末
viw                 # 选中当前单词
vib                 # 选中小括号内的东西
vi)                 # 选中小括号内的东西
vi]                 # 选中中括号内的东西
viB                 # 选中大括号内的东西
vi}                 # 选中大括号内的东西
vis                 # 选中句子中的东西
vab                 # 选中小括号内的东西（包含小括号本身）
va)                 # 选中小括号内的东西（包含小括号本身）
va]                 # 选中中括号内的东西（包含中括号本身）
vaB                 # 选中大括号内的东西（包含大括号本身）
va}                 # 选中大括号内的东西（包含大括号本身）
gv                  # 重新选择上一次选中的文字
:set paste          # 允许粘贴模式（避免粘贴时自动缩进影响格式）
:set nopaste        # 禁止粘贴模式
"?yy                # 复制当前行到寄存器 ? ，问号代表 0-9 的寄存器名称
"?d3j               # 删除光标下三行内容，并放到寄存器 ? ，问号代表 0-9 的寄存器名称
"?p                 # 将寄存器 ? 的内容粘贴到光标后
"?P                 # 将寄存器 ? 的内容粘贴到光标前
:registers          # 显示所有寄存器内容
:[range]y           # 复制范围，比如 :20,30y 是复制20到30行，:10y 是复制第十行
:[range]d           # 删除范围，比如 :20,30d 是删除20到30行，:10d 是删除第十行
ddp                 # 交换两行内容：先删除当前行复制到寄存器，并粘贴
"_[command]         # 使用[command]删除内容，并且不进行复制（不会污染寄存器）
"*[command]         # 使用[command]复制内容到系统剪贴板（需要vim版本有clipboard支持）
```



## 文本对象

```bash
$                   # 到行末
0                   # 到行首
^                   # 到行首非空字符
tx                  # 光标位置到字符 x 之前
fx                  # 光标位置到字符 x 之处
iw                  # 整个单词（不包括分隔符）
aw                  # 整个单词（包括分隔符）
iW                  # 整个 WORD（不包括分隔符）
aW                  # 整个 WORD（包括分隔符）
is                  # 整个句子（不包括分隔符）
ib                  # 小括号内
ab                  # 小括号内（包含小括号本身）
iB                  # 大括号内
aB                  # 大括号内（包含大括号本身）
i)                  # 小括号内
a)                  # 小括号内（包含小括号本身）
i]                  # 中括号内
a]                  # 中括号内（包含中括号本身）
i}                  # 大括号内
a}                  # 大括号内（包含大括号本身）
i'                  # 单引号内
a'                  # 单引号内（包含单引号本身）
i"                  # 双引号内
a"                  # 双引号内（包含双引号本身）
2i)                 # 往外两层小括号内
2a)                 # 往外两层小括号内（包含小括号本身）
2f)                 # 到第二个小括号处
2t)                 # 到第二个小括号前
```



## 查找替换

```bash
/pattern            # 从光标处向文件尾搜索 pattern
?pattern            # 从光标处向文件头搜索 pattern
n                   # 向同一方向执行上一次搜索
N                   # 向相反方向执行上一次搜索
*                   # 向前搜索光标下的单词
#                   # 向后搜索光标下的单词
:s/p1/p2/g          # 将当前行中全替换p1为p2
:%s/p1/p2/g         # 将当前文件中全替换p1为p2
:%s/p1/p2/gc        # 将当前文件中全替换p1为p2，并且每处询问你是否替换
:10,20s/p1/p2/g     # 将第10到20行中所有p1替换为p2
:%s/1\\2\/3/123/g   # 将“1\2/3” 替换为 “123”（特殊字符使用反斜杠标注）
:%s/\r//g           # 删除 DOS 换行符 ^M
```



## 可视模式

```bash
v                   # 开始可视模式
V                   # 开始可视行模式
Ctrl-V              # 开始可视块模式
>                   # 增加缩进
<                   # 减少缩进
d                   # 删除高亮选中的文字
x                   # 删除高亮选中的文字
c                   # 改写文字，即删除高亮选中的文字并进入插入模式
s                   # 改写文字，即删除高亮选中的文字并进入插入模式
y                   # 拷贝文字
~                   # 转换大小写
o                   # 跳转到标记区的另外一端
O                   # 跳转到标记块的另外一端
u                   # 标记区转换为小写
U                   # 标记区转换为大写
g Ctrl-G            # 显示所选择区域的统计信息
ggVG                # 选择全文
esc                 # 按esc键退出可视模式
```



## 注释命令

**多行注释**
```bash
Ctrl+v              # 进入命令行模式，按Ctrl + v进入可视模式，然后按j, 或者k选中多行，把需要注释的行标记起来
I                   # 按大写字母I，再插入注释符，例如#、//
esc                 # 按esc键就会全部注释了
```

**取消多行注释**

```bash
Ctrl+v              # 进入命令行模式，按Ctrl + v进入可视模式，按字母l横向选中列的个数，例如#、//（需要选中2列）
j 或 k              # 按字母j，或者k选中注释符号
d                   # 按d键就可全部取消注释
```

**复杂注释**

```bash
:起始行号,结束行号s/^/注释符/g（注意冒号）       # 在指定的行首添加注释
:起始行号,结束行号s/^注释符//g（注意冒号）       # 在指定的行首取消注释

:3,5 s/^/#/g        # 注释第3-5行
:3,5 s/^#//g        # 解除3-5行的注释

:1,$ s/^/#/g        # 注释整个文档
:1,$ s/^#//g        # 取消注释整个文档

:%s/^/#/g           # 注释整个文档，此法更快
:%s/^#//g           # 取消注释整个文档
```



## 位置跳转

```bash
Ctrl-O              # 跳转到上一个位置
Ctrl-I              # 跳转到下一个位置
Ctrl-^              # 跳转到 alternate file (当前窗口的上一个文件）
%                   # 跳转到 {} () [] 的匹配
gd                  # 跳转到局部定义（光标下的单词的定义）
gD                  # 跳转到全局定义（光标下的单词的定义）
gf                  # 打开名称为光标下文件名的文件
[[                  # 跳转到上一个顶层函数（比如C语言以大括号分隔）
]]                  # 跳转到下一个顶层函数（比如C语言以大括号分隔）
[m                  # 跳转到上一个成员函数
]m                  # 跳转到下一个成员函数
[{                  # 跳转到上一处未匹配的 {
]}                  # 跳转到下一处未匹配的 }
[(                  # 跳转到上一处未匹配的 (
])                  # 跳转到下一处未匹配的 )
[c                  # 上一个不同处（diff时）
]c                  # 下一个不同处（diff时）
[/                  # 跳转到 C注释开头
]/                  # 跳转到 C注释结尾
``                  # 回到上次跳转的位置
''                  # 回到上次跳转的位置
`.                  # 回到上次编辑的位置
'.                  # 回到上次编辑的位置
```



## 文件操作

```bash
:w                  # 保存文件
:w <filename>       # 按名称保存文件
:e <filename>       # 打开文件并编辑
:saveas <filename>  # 另存为文件
:o <filename>       # 在当前窗口打开另一个文件
:r <filename>       # 读取文件并将内容插入到光标后
:r !dir             # 将 dir 命令的输出捕获并插入到光标后
:only               # 关闭除光标所在的窗口之外的其他窗口
:close              # 关闭光标所在窗口的文件
:q                  # 关闭光标所在的窗口并退出
:q!                 # 强制退出
:qa！               # 关闭所有窗口(不保存)
:wa                 # 保存所有文件
:cd <path>          # 切换 Vim 当前路径
:pwd                # 显示 Vim 当前路径
:new                # 打开一个新的窗口编辑新文件
:enew               # 在当前窗口创建新文件
:vnew               # 在左右切分的新窗口中编辑新文件
:tabnew             # 在新的标签页中编辑新文件
```



## 已打开文件操作

```bash
:ls                 # 查案缓存列表
:bn                 # 切换到下一个缓存
:bp                 # 切换到上一个缓存
:bd                 # 删除缓存
:b 1                # 切换到1号缓存
:b abc              # 切换到文件名为 abc 开头的缓存
:badd <filename>    # 将文件添加到缓存列表
:set hidden         # 设置隐藏模式（未保存的缓存可以被切换走，或者关闭）
:set nohidden       # 关闭隐藏模式（未保存的缓存不能被切换走，或者关闭）
n Ctrl-^            # 切换缓存，先输入数字的缓存编号，再按 Ctrl + 6
```



## 窗口操作

```bash
:sp <filename>      # 上下切分窗口并在新窗口打开文件 filename
:vs <filename>      # 左右切分窗口并在新窗口打开文件 filename
:split              # 将当前窗口再复制一个纵向窗口出来，内容同步，游标可以不同
:vsplit             # 将当前窗口再复制一个横向窗口出来，内容同步，游标可以不同
vim -o file1 file2  # 终端中要打开vim文件时，横向分割显示多个文件
vim -O file1 file2  # 终端中要打开vim文件时，纵向分割显示多个文件
Ctrl-W s            # 上下切分窗口
Ctrl-W v            # 左右切分窗口
Ctrl-W w            # 循环切换到下一个窗口
Ctrl-W W            # 循环切换到上一个窗口
Ctrl-W p            # 跳到上一个访问过的窗口
Ctrl-W c            # 关闭当前窗口
Ctrl-W o            # 关闭其他窗口
Ctrl-W h            # 跳到左边的窗口
Ctrl-W j            # 跳到下边的窗口
Ctrl-W k            # 跳到上边的窗口
Ctrl-W l            # 跳到右边的窗口
Ctrl-W +            # 增加当前窗口的行高，前面可以加数字
Ctrl-W -            # 减少当前窗口的行高，前面可以加数字
Ctrl-W <            # 减少当前窗口的列宽，前面可以加数字
Ctrl-W >            # 增加当前窗口的列宽，前面可以加数字
Ctrl-W =            # 让所有窗口宽高相同
Ctrl-W H            # 将当前窗口移动到最左边
Ctrl-W J            # 将当前窗口移动到最下边
Ctrl-W K            # 将当前窗口移动到最上边
Ctrl-W L            # 将当前窗口移动到最右边
Ctrl-W x            # 交换窗口
Ctrl-W f            # 在新窗口中打开名为光标下文件名的文件
Ctrl-W gf           # 在新标签页中打开名为光标下文件名的文件
Ctrl-W R            # 旋转窗口
Ctrl-W T            # 将当前窗口移到新的标签页中
Ctrl-W P            # 跳转到预览窗口
Ctrl-W z            # 关闭预览窗口
Ctrl-W _            # 纵向最大化当前窗口
Ctrl-W |            # 横向最大化当前窗口
```



## 标签页

```bash
:tabs               # 显示所有标签页
:tabe <filename>    # 在新标签页中打开文件 filename
:tabn               # 下一个标签页
:tabp               # 上一个标签页
:tabc               # 关闭当前标签页
:tabo               # 关闭其他标签页
:tabn n             # 切换到第n个标签页，比如 :tabn 3 切换到第三个标签页
:tabm n             # 标签移动
:tabfirst           # 切换到第一个标签页
:tablast            # 切换到最后一个标签页
:tab help           # 在标签页打开帮助
:tab drop <file>    # 如果文件已被其他标签页和窗口打开则跳过去，否则新标签打开
:tab split          # 在新的标签页中打开当前窗口里的文件
:tab ball           # 将缓存中所有文件用标签页打开
:set showtabline=?  # 设置为 0 就不显示标签页标签，1会按需显示，2会永久显示
ngt                 # 切换到第n个标签页，比如 2gt 将会切换到第二个标签页
gt                  # 下一个标签页
gT                  # 上一个标签页
```



## 书签

```bash
:marks              # 显示所有书签
ma                  # 保存当前位置到书签 a ，书签名小写字母为文件内，大写全局
'a                  # 跳转到书签 a所在的行
`a                  # 跳转到书签 a所在位置
`.                  # 跳转到上一次编辑的行
'A                  # 跳转到全文书签 A
['                  # 跳转到上一个书签
]'                  # 跳转到下一个书签
'<                  # 跳到上次可视模式选择区域的开始
'>                  # 跳到上次可视模式选择区域的结束
```
 


## 常用设置

```bash
:set nocompatible   # 设置不兼容原始 vi 模式（必须设置在最开头）
:set bs=?           # # 设置BS键模式，现代编辑器为 :set bs=eol,start,indent
:set sw=4           # 设置缩进宽度为 4
:set ts=4           # 设置制表符宽度为 4
:set noet           # 设置不展开 tab 成空格
:set et             # 设置展开 tab 成空格
:set winaltkeys=no  # 设置 GVim 下正常捕获 ALT 键
:set nowrap         # 关闭自动换行
:set ttimeout       # 允许终端按键检测超时（终端下功能键为一串ESC开头的扫描码）
:set ttm=100        # 设置终端按键检测超时为100毫秒
:set term=?         # 设置终端类型，比如常见的 xterm
:set ignorecase     # 设置搜索是否忽略大小写
:set smartcase      # 智能大小写，默认忽略大小写，除非搜索内容里包含大写字母
:set list           # 设置显示制表符和换行符
:set nu             # 设置显示行号，禁止显示行号可以用 :set nonu
:set number         # 设置显示行号，禁止显示行号可以用 :set nonumber
:set relativenumber # 设置显示相对行号（其他行与当前行的距离）
:set paste          # 进入粘贴模式（粘贴时禁用缩进等影响格式的东西）
:set nopaste        # 结束粘贴模式
:set spell          # 允许拼写检查
:set hlsearch       # 设置高亮查找
:set ruler          # 总是显示光标位置
:set incsearch      # 查找输入时动态增量显示查找结果
:set insertmode     # Vim 始终处于插入模式下，使用 Ctrl-o 临时执行命令
:set all            # 列出所有选项设置情况
:syntax on          # 允许语法高亮
:syntax off         # 禁止语法高亮
```



## 帮助信息

```bash
:h tutor            # 入门文档
:h quickref         # 快速帮助
:h index            # 查询 Vim 所有键盘命令定义
:h summary          # 帮助你更好的使用内置帮助系统
:h Ctrl-H           # 查询普通模式下 Ctrl-H 是干什么的
:h i_Ctrl-H         # 查询插入模式下 Ctrl-H 是干什么的
:h i_<Up>           # 查询插入模式下方向键上是干什么的
:h pattern.txt      # 正则表达式帮助
:h eval             # 脚本编写帮助
:h function-list    # 查看 VimScript 的函数列表 
:h windows.txt      # 窗口使用帮助
:h tabpage.txt      # 标签页使用帮助
:h +timers          # 显示对 +timers 特性的帮助
:h :!               # 查看如何运行外部命令
:h tips             # 查看 Vim 内置的常用技巧文档
:h set-termcap      # 查看如何设置按键扫描码
:viusage            # NORMAL 模式帮助
:exusage            # EX 命令帮助
:version            # 显示当前 Vim 的版本号和特性
```



# 外部命令

```bash
:!ls                # 运行外部命令 ls，并等待返回
:r !ls              # 将外部命令 ls 的输出捕获，并插入到光标后
:w !sudo tee %      # sudo以后保存当前文件
:call system('ls')  # 调用 ls 命令，但是不显示返回内容
:!start notepad     # Windows 下启动 notepad，最前面可以加 silent
:sil !start cmd     # Windows 下当前目录打开 cmd
:%!prog             # 运行文字过滤程序，如整理 json格式 :%!python -m json.tool
```



## Quickfix 窗口

```bash
:copen              # 打开 quickfix 窗口（查看编译，grep等信息）
:copen 10           # 打开 quickfix 窗口，并且设置高度为 10
:cclose             # 关闭 quickfix 窗口
:cfirst             # 跳到 quickfix 中第一个错误信息
:clast              # 跳到 quickfix 中最后一条错误信息
:cc [nr]            # 查看错误 [nr]
:cnext              # 跳到 quickfix 中下一个错误信息
:cprev              # 跳到 quickfix 中上一个错误信息
```



## 拼写检查

```bash
:set spell          # 打开拼写检查
:set nospell        # 关闭拼写检查
]s                  # 下一处错误拼写的单词
[s                  # 上一处错误拼写的单词
zg                  # 加入单词到拼写词表中
zug                 # 撤销上一次加入的单词
z=                  # 拼写建议
```



## 代码折叠

```bash
za                  # 切换折叠
zA                  # 递归切换折叠
zc                  # 折叠光标下代码
zC                  # 折叠光标下所有代码
zd                  # 删除光标下折叠
zD                  # # 递归删除所有折叠
zE                  # 删除所有折叠
zf                  # 创建代码折叠
zF                  # 指定行数创建折叠
zi                  # 切换折叠
zm                  # 所有代码折叠一层
zr                  # 所有代码打开一层
zM                  # 折叠所有代码，设置 foldlevel=0，设置 foldenable
zR                  # 打开所有代码，设置 foldlevel 为最大值
zn                  # 折叠 none，重置 foldenable 并打开所有代码
zN                  # 折叠 normal，重置 foldenable 并恢复所有折叠
zo                  # 打开一层代码
zO                  # 打开光标下所有代码折叠
```



## 文档加密解密


**文档加密**

```bash
vim -x file_name	# 输入加密密码 -> 确认密码! 注意：不修改内容也要保存。:wq，不然密码设定不会生效。
:X 			# 已打开文件并在命令行模式下，输入加密密码 -> 确认密码! 注意：不修改内容也要保存。:wq，不然密码设定不会生效。
:set key=密码		# 已打开文件并在命令行模式下，输入加密密码 -> 确认密码! 注意：不修改内容也要保存。:wq，不然密码设定不会生效。
```

**文档解密**

```bash
:X 			# 已打开文件并在命令行模式下，提示输入密码，不输入而是按 Enter。注意：不修改内容也要保存。:wq，不然解密设定不会生效。
:set key=		# 已打开文件并在命令行模式下，设置key的密码为空。注意：不修改内容也要保存。:wq，不然密码设定不会生效。
```



## 宏录制

```bash
qa                  # 开始录制名字为 a 的宏
q                   # 结束录制宏
@a                  # 播放名字为 a 的宏
@@                  # 播放上一个宏
@:                  # 重复上一个ex命令（即冒号命令）
```



## 其他命令

```bash
Ctrl-X Ctrl-F       # 插入模式下文件路径补全
Ctrl-X Ctrl-O       # 插入下 Omnifunc 补全
Ctrl-X Ctrl-N       # 插入模式下关键字补全
Ctrl-X Ctrl-E       # 插入模式下向上滚屏
Ctrl-X Ctrl-Y       # 插入模式下向下滚屏
Ctrl-E              # 向上滚屏
Ctrl-Y              # 向下滚屏
Ctrl-G              # 显示正在编辑的文件名，以及大小和位置信息
g Ctrl-G            # 显示文件的：大小，字符数，单词数和行数，可视模式下也可用
zz                  # 调整光标所在行到屏幕中央
zt                  # 调整光标所在行到屏幕上部
zb                  # 调整光标所在行到屏幕下部
ga                  # 显示光标下字符的 ascii 码或者 unicode 编码
g8                  # 显示光标下字符的 utf-8 编码字节序
gi                  # 回到上次进入插入的地方，并切换到插入模式
K                   # 查询光标下单词的帮助
ZZ                  # 保存文件（如果有改动的话），并关闭窗口
ZQ                  # 不保存文件关闭窗口
Ctrl-PgUp           # 上个标签页，GVim OK，部分终端软件需设置对应键盘码
Ctrl-PgDown         # 下个标签页，GVim OK，部分终端软件需设置对应键盘码
Ctrl-R Ctrl-W       # 命令模式下插入光标下单词
Ctrl-INSERT         # 复制到系统剪贴板（GVIM）
SHIFT-INSERT        # 粘贴系统剪贴板的内容（GVIM）
:set ff=unix        # 设置换行为 unix
:set ff=dos         # 设置换行为 dos
:set ff?            # 查看换行设置
:set nohl           # 清除搜索高亮
:set termcap        # 查看会从终端接收什么以及会发送给终端什么命令
:set guicursor=     # 解决 SecureCRT/PenguiNet 中 NeoVim 局部奇怪字符问题
:set t_RS= t_SH=    # 解决 SecureCRT/PenguiNet 中 Vim8.0 终端功能奇怪字符
:set fo+=a          # 开启文本段的实时自动格式化
:earlier 15m        # 回退到15分钟前的文件内容
:.!date             # 在当前窗口插入时间
:%!xxd              # 开始二进制编辑
:%!xxd -r           # 保存二进制编辑
:r !curl -sL {URL}  # 读取 url 内容添加到光标后
:g/^\s*$/d          # 删除空行
:g/green/d          # 删除所有包含 green 的行
:v/green/d          # 删除所有不包含 green 的行
:g/gladiolli/#      # 搜索单词打印结果，并在结果前加上行号
:g/ab.*cd.*efg/#    # 搜索包含 ab,cd 和 efg 的行，打印结果以及行号
:v/./,/./-j         # 压缩空行
:Man bash           # 在 Vim 中查看 man，先调用 :runtime! ftplugin/man.vim 激活
/fred\|joe          # 搜索 fred 或者 joe
/\<\d\d\d\d\>       # 精确搜索四个数字
/^\n\{3}            # 搜索连续三个空行
```



## 插件 - [vim-commentary](https://github.com/tpope/vim-commentary)

```bash
gcc                 # 注释当前行
gc{motion}          # 注释 {motion} 所标注的区域，比如 gcap 注释整段
gci{                # # 注释大括号内的内容
gc                  # 在 Visual Mode 下面按 gc 注释选中区域
:7,17Commentary     # # # 注释 7 到 17 行
```



## 插件 - [vim-easy-align](https://github.com/junegunn/vim-easy-align)

```bash
:EasyAlign =        # 以第一个匹配的=为中心对齐
:EasyAlign *=       # 匹配并且对齐所有=
```



## 插件 - [vim-unimpaired](https://github.com/tpope/vim-unimpaired)

```bash
[space              # 向上插入空行
]space              # 向下插入空行
[e                  # 替换当前行和上一行
]e                  # 替换当前行和下一行
[x                  # XML 编码
]x                  # XML 解码
[u                  # URL 编码
]u                  # URL 解码
[y                  # C 字符串编码
]y                  # C 字符串解码
[q                  # 上一个 quickfix 错误
]q                  # 下一个 quickfix 错误
[Q                  # 第一个 quickfix 错误
]Q                  # 最后一个 quickfix 错误
[f                  # 切换同目录里上一个文件
]f                  # 切换同目录里下一个文件
[os                 # 设置 :set spell
]os                 # 设置 :set nospell
=os                 # 设置 :set invspell
[on                 # 显示行号
]on                 # 关闭行号
[ol                 # 显示回车和制表符 :set list
]ol                 # 不显示回车和制表符 :set nolist
[b                  # 缓存切换到上一个文件，即 :bp
]b                  # 缓存切换到下一个文件，即 :bn
[B                  # 缓存切换到第一个文件，即 :bfirst
]B                  # 缓存切换到最后一个文件，即 :blast
```



## 插件 - [asyncrun.vim](https://github.com/skywind3000/asyncrun.vim)

```bash
:AsyncRun ls        # 异步运行命令 ls 结果输出到 quickfix 使用 :copen 查看
:AsyncRun -raw ls   # 异步运行命令 ls 结果不匹配 errorformat
```



## 插件 - [vim-textobj-argument](https://github.com/gaving/vim-textobj-argument)

```bash
cia                 # 改写函数参数
caa                 # 改写函数参数（包括逗号分隔）
dia                 # 删除函数参数
daa                 # 删除函数参数（包括逗号分隔）
via                 # 选取函数参数
vaa                 # 选取函数参数（包括逗号分隔）
yia                 # 复制函数参数
yaa                 # 复制函数参数（包括逗号分隔）
```



## 网络资源

- 最新版本            https://github.com/vim/vim   
- Windows 最新版      https://github.com/vim/vim-win32-installer/releases
- 插件浏览            http://vimawesome.com
- 正确设置ALT/BS键    http://www.skywind.me/blog/archives/2021
- 视频教程            http://vimcasts.org/
- 中文帮助            http://vimcdoc.sourceforge.net/doc/help.html
- 中文版入门到精通    https://github.com/wsdjeg/vim-galore-zh_cn
- 五分钟脚本入门      http://www.skywind.me/blog/archives/2193
- 脚本精通            http://learnvimscriptthehardway.stevelosh.com/
- 中文脚本帮助        vimcdoc.sourceforge.net/doc/eval.html
- 十六年使用经验      http://zzapper.co.uk/vimtips.html
- 配色方案            http://vimcolors.com/



## TIPS

- 永远不要用 Ctrl-C 代替 <ESC> 完全不同的含义，容易错误中断运行的后台脚本
- 很多人使用 Ctrl-[ 代替 <ESC>，左手小指 Ctrl，右手小指 [ 熟练后很方便
- 某些终端中使用 Vim 8 内嵌终端如看到奇怪字符，使用 :set t_RS= t_SH= 解决
- 某些终端中使用 NeoVim 如看到奇怪字符，使用 :set guicursor= 解决
- 多使用 ciw, ci[, ci", ci( 以及 diw, di[, di", di( 命令来快速改写/删除文本
- 在行内左右移动光标时，多使用w b e或W B E，而不是h l或方向键，这样会快很多
- SHIFT 相当于移动加速键， w b e 移动光标很慢，但是 W B E 走的很快
- 自己要善于总结新技巧，比如移动到行首非空字符时用 0w 命令比 ^ 命令更容易输入
- 在空白行使用 dip 命令可以删除所有临近的空白行，viw 可以选择连续空白
- 缩进时使用 >8j  >}  <ap  >ap  =i}  == 会方便很多
- 插入模式下，当你发现一个单词写错了，应该多用 Ctrl-W 这比 <BackSpace> 快
- y d c 命令可以很好结合 f t 和 /X 比如 dt) 和 y/end<cr>
- c d x 命令会自动填充寄存器 "1 到 "9 , y 命令会自动填充 "0 寄存器
- 用 v 命令选择文本时，可以用 o 掉头选择，有时很有用
- 写文章时，可以写一段代码块，然后选中后执行 :!python 代码块就会被替换成结果
- 搜索后经常使用 :nohl 来消除高亮，使用很频繁，可以 map 到 <BackSpace> 上
- 搜索时可以用 Ctrl-R Ctrl-W 插入光标下的单词，命令模式也能这么用
- 映射按键时，应该默认使用 noremap ，只有特别需要的时候使用 map
- 当你觉得做某事很低效时，你应该停下来，u u u u 然后思考正确的高效方式来完成
- 用 y复制文本后，命令模式中 Ctrl-R 然后按双引号 0 可以插入之前复制内容
- Windows 下的 GVim 可以设置 set rop=type:directx,renmode:5 增强显示



# 参考

- https://github.com/skywind3000/awesome-cheatsheets/blob/master/editors/vim.txt
- https://github.com/groenewege/vimrc/blob/master/vim_cheat_sheet.txt
- http://blog.g-design.net/post/4789778607/vim-cheat-sheet
- http://www.keyxl.com/aaa8263/290/VIM-keyboard-shortcuts.htm
- http://jmcpherson.org/editing.html
- http://www.fprintf.net/vimCheatSheet.html
- http://www.ouyaoxiazai.com/article/24/654.html
- http://bbs.it-home.org/thread-80794-1-1.html
- http://www.lpfrx.com/wp-content/uploads/2008/09/vi.jpg
- http://michael.peopleofhonoronly.com/vim/
- https://github.com/hobbestigrou/vimtips-fortune/blob/master/fortunes/vimtips
- https://github.com/glts/vim-cottidie/blob/master/autoload/cottidie/tips




---





