# In-TeX/LaTeX 简介

In-TeX/LaTeX 是基于 LaTeX 排版系统、面向 InDesign 提供公式排版解决方案的脚本程序，它有如下特点：

1. 跨平台性：这个解决方案主要依赖跨平台的 LaTeX 系统，在 InDesign 里采用 JavaScript 即 Adobe 的 ExtendScript 开发，保证了跨平台，不管是 Windows 和 Mac 系统都能使用。
2. 运行速度：因为公式的生成完全依赖 LaTeX 编译，所以 LaTeX 编译的速度很大程度上决定了脚本运行的快慢，为此本解决方案还专门提供了智能切换引擎的方式，生成公式时尽可能采用更快的 pdflatex 引擎编译，公式中含有中文时使用支持中文的 xelatex 引擎编译。而且也提供支持编译速度最快的 ApTeX (Asiatic pTeX) 引擎(platex-ng 的新命名)。
3. 使用便捷：具有插入转换、获取修改，代码还原，批处理、公式调整等功能，并提供使用 LaTeX 模版方式，是本解决方案的一大特色，通过自定义模版应付更复杂的 LaTeX 应用场景。

4. 拓展性：本解决方案不仅适用于数理化公式排版，LaTeX 有着丰富的宏包资源，发挥你的想象，在 InDesign 里直接把 LaTeX 代码转换为 PDF 输出结果插入，各种数据图表、作图等就呈现在你的 InDesign 版面中。

5. 版本限制：本解决方案主要是采用 JavaScript 语言开发，界面完全依赖 Adobe ExtendScript ScriptUI，在不同系统平台、不同 InDesign 版本上会有些小差异，甚至带来操作表现差异上的困惑，所以特别限定了至少 InDesign CS6 环境来运行。


和别人的公式排版解决方案有什么不同：

1. 基于 LaTeX ，完美的公式。
2. 跨平台。至少国内的其他解决方案只是给出 PC 解决。
3. 更多的拓展性。基于 LaTeX 就可以在数学公式排版之外多加很多拓展，物理、化学公式之类的排版也是可行的，而且 LaTeX 宏包异常丰富，甚至可以把作图功能集成到 InDesign 里，自动转化数据为图表等，这些是 MathType 无法企及的功能。所以，即使你已经在用了别人的 MathType 公式排版解决方案，但别人那里没有这方面的功能，选择本方案也是一种很好的补充。
4. 与以前的 IDMath 一类日本人做出的免费的也是基于 LaTeX 的公式工具相比，本解决方案有更多的功能和人性化设计操作，我计划以后有更多功能的丰富拓展，这些足以让你感到惊喜。



# In-TeX/LaTeX 安装和使用

## 一、LaTeX 系统环境安装

### Windows 用户：

不管你是用的哪个 LaTeX 发行版本，但至少你的 LaTeX 环境必须安装有 Perl 和 Ghostscript，版本要求至少 Perl5，Ghostscript 需满足 >= 8.0，如果你已安装的 LaTeX 系统没有这些或者版本太低，请安装或者升级新版本，如果你的 LaTeX 环境里没有 pdfcrop 还需要自行安装，只要不是太老的 LaTeX 发行版本一般都是自带 pdfcrop 。对于不方便安装或升级 LaTeX 最新发行版本的，特指那些 CTeX 套件老用户，如 CTeX 2.4.6 一类的老老用户，我建议使用网友制作的、包含比较新不太旧 ctex 宏包的 TeXLive 绿色安装版本，如 TeXLive2016 绿色版本(后附有介绍和下载)，因 Windows 下本解决方案不依赖 LaTeX 在系统中的环境变量来运行，对于不喜欢折腾的用户使用绿色版本 TeXLive 是个很好的选择。

总之，没有特殊情况优先推荐安装 TeXLive 发行版本，而且是最新版本的(注：TeXLive2018 已不支持 XP 系统)，各种宏包更新维护都很方便。如果你对 LaTeX 系统很熟悉，完全可以定制你的 LaTeX 环境，如选择 W32TeX，根据你的需要自行安装控制体积的大小，前面提到的 Perl 和 Ghostscript 环境同样也是必须安装、满足版本要求的。

### Mac 用户：

推荐安装 MacTeX 2018（最新的 ctex 宏包有所更新，增加了对 OSX 新版系统中文字库的自动识别支持） 即可，或者更新版本 MacTeX。

## 二、In-TeX/LaTeX 脚本安装

Windows 和 Mac 通用的安装方法推荐这样操作：

解压缩后把 InTeXLaTeX 文件夹（如文件夹名是类似 InTeXLaTeX_3.14_V20200920 这样带有的版本号，最好请先修改文件夹名为 InTeXLaTeX），在你的 InDesign 打开的情况下，菜单选择，「窗口」 --> 「实用程序」 --> 「脚本」， 在「脚本」面板中选择「用户」，然后右键，选择「在访达中打开」(Mac) /「在资源管理器中显示」(Windows)，在弹出的文件夹下有个「Scripts Panel」文件夹，把这个「 InTeXLaTeX」文件夹放入「Scripts Panel」中，在「脚本」面板里依次打开「用户」－ 「InTeXLaTeX」，找到 InTeXLaTeX 脚本文件双击即运行，按提示配置 LaTeX 引擎后即可玩转 LaTeX 公式。

以上安装方法避免了安装在其它某些文件夹下可能需要管理员权限运行 InDesign 才能使用公式脚本的问题。

免费用户：自动生成免费版本的授权文件，不能使用需要付费的功能。

付费用户：需要在特别插件授权环境下运行，使用另外的授权文件运行完全功能，付款购买后请联系作者相关操作事宜。

## 三、In-TeX/LaTeX 的使用

使用很简单，按提示操作即可，更多功能参照提供的视频演示和模版(技术支持QQ群 广之源 InDesign 1群 10569122 共享里提供)。没有付费授权的版本不支持批处理转换公式和调整公式的功能(注：免费版本仅支持当前行公式自动调整)，操作涉及被限制的功能会有提示，需要这些功能的请联系作者购买授权，如果免费版本已经满足你的需求并期待更完善的功能升级，点击界面当中的帮助按钮，扫一扫二维码支付宝赞助一下 9.97￥！最重要的是加入 InTeXLaTeX 技术支持群 广之源 InDesign 1群 10569122，获取即时的帮助，反馈问题和讨论技术。LaTeX 毕竟是不简单的排版软件，多知道一些乐趣多一些，少些困惑少走弯路。

## 四、LaTeX 资源

### 论坛及网站等

~~http://bbs.ctex.org/forum.php  中文TeX社区~~

http://www.latexstudio.net LaTeX工作室

https://zhuanlan.zhihu.com/LaTeX  All about TeXnique（能提升你对TeX理解的东西）

https://weibo.com/latexstudio LaTeX科技排版 新浪微博

https://weibo.com/cooldtp @广之源Skin 新浪微博(关于本解决方案及 InDesign 相关的最新资讯发布)

InTeXLaTeX 官方技术支持 QQ 群： 广之源 InDesign 1群 10569122

LaTeX技术交流5000人QQ群（91940767）(~~需付费入群，~~有很多 LaTeX 技术高手可交流)

### LaTeX 中文资料相关

lshort 中文版、LaTeX 入门(刘海洋)、LaTeX2e完全学习手册 第二版（胡伟）等。

### TeXLive／MacTeX 等下载

#### 1、TeX套装下载

http://www.latexstudio.net/page/texsoftware

#### 2、绿色版本 TeXLive 下载

texlive2018+sumatrapdf(32bit)+texstudio(32bit)便携版百度网盘下载：

https://pan.baidu.com/s/1ZC7Ivg1cI64-Jl6FhP-irA

密码：ks13

~~TeXLive 2016 ISO 绿色免安装版本 for windows 介绍：~~

~~http://bbs.ctex.org/forum.php?mod=viewthread&tid=152717~~

TeXLive 2016 ISO 绿色免安装版本 for windows 百度网盘下载(请选择 /TeX 文件夹下的 TeXLIve2016.iso.xz 下载，相关信息参照 TeXLive2016.txt 文件的说明)：

https://pan.baidu.com/s/1brg3hj5

#### ~~3、W32TeX 下载~~

~~http://w32tex.org/index-zh.html~~

#### 4、ApTeX (Asiatic pTeX／ptex-ng) 项目

https://github.com/clerkma/ptex-ng

https://github.com/clerkma/ptex-ng-dist

#### 5、Perl & Ghostscript 下载

ActivePerl (安装时请注意有勾选的选项，不推荐安装附带的编辑器)：https://www.activestate.com/activeperl/downloads

Ghostscript：https://www.ghostscript.com/download/gsdnld.html

#### 6、In-TeX/LaTeX 网盘下载

In-TeX/LaTeX 最新版本除了在技术支持 QQ 群10569122 共享里可下载，还可以在以下网盘链接下载(包括样本、操作演示视频等)：

链接: https://pan.baidu.com/s/1NGO3z5D-wWgjkpAVnLCatQ?pwd=2kqm 提取码: 2kqm

或 Github：https://github.com/cooldtp/InTeXLaTeX

最后特别推荐一款可抓屏 OCR 公式图片为 LaTeX 公式代码的免费工具——Mathpix，Mac 及 Win 版本均有，让你录入公式事半功倍：

 https://www.mathpix.com/



PUB@2018年9月1日 By Skin 于南宁

upDate: 2023-06-27

新浪微博：@广之源Skin

联系方式：QQ150062840

技术支持：QQ群10569122
