不管管任何编程语言，最基础的数据只有两种，一是数值、二是字符。

<h1>数值</h1>

从小学、初中、高中到大学，会有10多年的的数学课程。而数学课程上所处理的东西就是数值。假定你是一个大学生，那么你也至少有12年的经验。哪怕你只是一个小学生，那么你也大概跟数值有5、6年的处理经验（学前班、幼儿园）。也就是说，我们在学习编程之前，几乎每个人都学过很多年的数学。

那么，我们可以简单的梳理一下。小学的四则运算、未知数等，中学的各种各样的类型的函数，大学的高等数学，一路走过来我们数学上学习的方法、概念越来越高级。但是我们所处理的东西却从未改变。

如 1、2、3…… 这样熟悉的<font color="blue">整数</font>，如 0.1、0.2…… 的<font color="blue">小数</font>等等。我们所处理的东西始终都是数值。

那么到了计算机上之后，我们碰到的第一个问题就是，数值如何存储在计算机上？

与我们平常计算数据不同的是，在计算机上的底层是使用二进制进行计算的。我们在学习本课程的时候不要求掌握二进制的使用，只需要能够了解某些数据使用二进制的推导过程即可。

首先我们要做的第一件事情，就是拿出一张草稿纸，来熟悉一下二进制和十进制的关系。

[code]
十进制  二进制
0       0
1       1
2       10
[/code]

十进制当中是满十进一位，而二进制是满二进一位。也就是说在十进制中 9 + 1 满十、进一位，个位变成 0 十位变成 1；而二进制中则是 1 + 1 满二、进一位，十位变成 1 个位变成 0。所以十进制的 2 对应二进制的 10。

按照这个思路我们继续往下写：

[code]
十进制  二进制
0       0
1       1
2       10
3       11
4       100
5       101
...
[/code]

<font color="blue">【课堂作业①】</font>请各位初学二进制的同学请把这个当做课堂上的作业，按照满二进一的方式，以此类推在草稿纸上一直往下写，写到十进制的 128 为止。

如果你有顺利的完成这个作业，我们可以简单的对几组数据，分别是：

[code]
十进制  二进制
...
65      1000001
...
127     1111111
128     10000000 
[/code]

如果你在草稿纸上推出来的数据与上方不符，可能需要检查一下了。


<h1>字符</h1>

在简单了解了数值在计算机上的存储之后，我们需要来了解一下计算机中的字符。首先我们需要清楚的概念是，内存上只能存储数值（二进制的数据）。

那么在计算机只能存储数值的情况下我们要如何跟别人的沟通？最简单的办法就是约定一个字典，比如我们互相约定 1代表A、2代表B、3代表C以此类推，26个字母分别由 1~26 来代表。那么我们在只能用数字的情况下也可以沟通了：

[code]
91215225251521
[/code]

<font color="blue">【课堂作业②】</font>那么，又到了课堂作业的时候了，大家可以翻出草稿纸，尝试一下用我们刚刚约定的规则来把上面这段数字变成英文。由于过程比较简单，所以博主不准备在课堂上讲解。当然如果你想很快知道答案的话，可以把这段数字写在小纸条上递给女生试试，据说女生非常擅长解这个（严肃脸）。

<font color="grey">（博主还是强调一下，碰到作业要先做完再继续往后看，不要欠作业。）</font>

这个作业做完之后，相信你已经对这个“读数字”的过程有了一定的了解，那么现在再来布置一个“写数字”的作业：

<font color="blue">【课堂作业③】</font>同样是英文26个字母，不过不想让人一看就能才出来，于是你决定在上面的基础上把每个字母的大小加10，让 a 从 11 开始， z 则是 36，如果碰到无法转换的地方则自己定义新的规则来填补。根据这个约定，让我们把英文 “How old are you? I am 18.” 转成数字。

如果有你认真的在草稿纸上研究这个作业的话，相信你一定会碰到如下问题：

<ol>
<li>约定的规则中无法区分字母的大小写。</li>
<li>约定的规则没有指定标点符号。</li>
<li>约定的规则没有指定数字如何用数字表示。</li></ol>

简单的来处理这些问题，我们可以自由的定义 37 为空格，38 为问号(?)，39 是句号(.)，然后从40开始则是 0、41 代表 1、42 代表 2……以此类推 49代表9。然后50留空，51开始是大写字母， A 从 51 开始， Z 则是 76 等等。

这种问题实际上是没有“正确答案”的，当然也不需要正确答案。博主这里只是给大家一个参考，大家也可以按照自己习惯的方式来定义规则把文字转成数字。

相信做完这两个作业之后，你已经对使用数字来存储文字有了一定的感觉。（如果你觉得添加各种规则变化很好玩、就这样不过瘾的话，推荐你去逛百度密码吧。）

实际上，这样用数字存储文字有一个很关键的地方，就是要双方都要用同样的约定好的规则才能正常的沟通。在计算机的领域中，早就有很多这样约定好的、使用数字存储文字的规则，我们通常把这些约定的规则称作“编码”。

最常见的编码要属计算机原产国（美国）制订的ASCII码了。其次国内比较常见的则是简体中文编码（GB2312），繁体中文编码（BIG5）。这些编码原理上没什么好说的，都是人为约定的，与我们刚刚作业上自定义的编码本质上来说没有什么不同，要说区别的话，只能说这些编码都是约定俗成、并且是大家都知道的。

现在让我们简单看一下 ASCII 码表。

<table class="wikitable" style="text-align:center;">
<tbody><tr>
<th><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E4%BA%8C%E8%BF%9B%E5%88%B6" title="二进制">二进制</a></th>
<th><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E5%8D%81%E8%BF%9B%E5%88%B6" title="十进制">十进制</a></th>
<th><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E5%8D%81%E5%85%AD%E8%BF%9B%E5%88%B6" title="十六进制">十六进制</a></th>
<th><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E7%B8%AE%E5%AF%AB" title="缩写">缩写</a></th>
<th><a rel="nofollow" href="http://zh.wikipedia.org/wiki/Unicode" title="Unicode">Unicode</a><br>
表示法</th>
<th><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E8%84%AB%E5%87%BA%E5%AD%97%E5%85%83&amp;action=edit&amp;redlink=1" class="new" title="脱出字符（页面不存在）">脱出字符</a><br>
表示法</th>
<th><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E5%90%8D%E7%A7%B0" title="名称">名称</a>／<a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E6%84%8F%E4%B9%89&amp;action=edit&amp;redlink=1" class="new" title="意义（页面不存在）">意义</a></th>
</tr>
<tr>
<td>0000&nbsp;0000</td>
<td><a rel="nofollow" href="http://zh.wikipedia.org/wiki/0" title="0">0</a></td>
<td>00</td>
<td><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=NUL&amp;action=edit&amp;redlink=1" class="new" title="NUL（页面不存在）">NUL</a></td>
<td>␀</td>
<td>^@</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E7%A9%BA%E5%AD%97%E7%AC%A6" title="空字符">空字符</a>（<a rel="nofollow" href="http://zh.wikipedia.org/wiki/Null" title="Null" class="mw-redirect">Null</a>）</td>
</tr>
<tr>
<td>0000&nbsp;0001</td>
<td><a rel="nofollow" href="http://zh.wikipedia.org/wiki/1" title="1">1</a></td>
<td>01</td>
<td><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=SOH&amp;action=edit&amp;redlink=1" class="new" title="SOH（页面不存在）">SOH</a></td>
<td>␁</td>
<td>^A</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E6%A0%87%E9%A2%98%E5%BC%80%E5%A7%8B&amp;action=edit&amp;redlink=1" class="new" title="标题开始（页面不存在）">标题开始</a></td>
</tr>
<tr>
<td>0000&nbsp;0010</td>
<td><a rel="nofollow" href="http://zh.wikipedia.org/wiki/2" title="2">2</a></td>
<td>02</td>
<td><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=STX&amp;action=edit&amp;redlink=1" class="new" title="STX（页面不存在）">STX</a></td>
<td>␂</td>
<td>^B</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E6%9C%AC%E6%96%87%E5%BC%80%E5%A7%8B&amp;action=edit&amp;redlink=1" class="new" title="本文开始（页面不存在）">本文开始</a></td>
</tr>
<tr>
<td>0000&nbsp;0011</td>
<td><a rel="nofollow" href="http://zh.wikipedia.org/wiki/3" title="3">3</a></td>
<td>03</td>
<td><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=ETX&amp;action=edit&amp;redlink=1" class="new" title="ETX（页面不存在）">ETX</a></td>
<td>␃</td>
<td>^C</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E6%9C%AC%E6%96%87%E7%BB%93%E6%9D%9F&amp;action=edit&amp;redlink=1" class="new" title="本文结束（页面不存在）">本文结束</a></td>
</tr>
<tr>
<td>0000&nbsp;0100</td>
<td><a rel="nofollow" href="http://zh.wikipedia.org/wiki/4" title="4">4</a></td>
<td>04</td>
<td><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=EOT&amp;action=edit&amp;redlink=1" class="new" title="EOT（页面不存在）">EOT</a></td>
<td>␄</td>
<td>^D</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E5%82%B3%E8%BC%B8%E7%BB%93%E6%9D%9F&amp;action=edit&amp;redlink=1" class="new" title="传输结束（页面不存在）">传输结束</a></td>
</tr>
<tr>
<td>0000&nbsp;0101</td>
<td><a rel="nofollow" href="http://zh.wikipedia.org/wiki/5" title="5">5</a></td>
<td>05</td>
<td><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=ENQ&amp;action=edit&amp;redlink=1" class="new" title="ENQ（页面不存在）">ENQ</a></td>
<td>␅</td>
<td>^E</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E8%AF%B7%E6%B1%82&amp;action=edit&amp;redlink=1" class="new" title="请求（页面不存在）">请求</a></td>
</tr>
<tr>
<td>0000&nbsp;0110</td>
<td><a rel="nofollow" href="http://zh.wikipedia.org/wiki/6" title="6">6</a></td>
<td>06</td>
<td><a rel="nofollow" href="http://zh.wikipedia.org/wiki/ACK" title="ACK" class="mw-disambig">ACK</a></td>
<td>␆</td>
<td>^F</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E7%A2%BA%E8%AA%8D%E5%9B%9E%E6%87%89&amp;action=edit&amp;redlink=1" class="new" title="确认回应（页面不存在）">确认回应</a></td>
</tr>
<tr>
<td>0000&nbsp;0111</td>
<td><a rel="nofollow" href="http://zh.wikipedia.org/wiki/7" title="7">7</a></td>
<td>07</td>
<td><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=BEL&amp;action=edit&amp;redlink=1" class="new" title="BEL（页面不存在）">BEL</a></td>
<td>␇</td>
<td>^G</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E5%93%8D%E9%93%83&amp;action=edit&amp;redlink=1" class="new" title="响铃（页面不存在）">响铃</a></td>
</tr>
<tr>
<td>0000&nbsp;1000</td>
<td><a rel="nofollow" href="http://zh.wikipedia.org/wiki/8" title="8">8</a></td>
<td>08</td>
<td><a rel="nofollow" href="http://zh.wikipedia.org/wiki/BS" title="BS" class="mw-disambig">BS</a></td>
<td>␈</td>
<td>^H</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E9%80%80%E6%A0%BC%E9%8D%B5&amp;action=edit&amp;redlink=1" class="new" title="退格键（页面不存在）">退格</a></td>
</tr>
<tr>
<td>0000&nbsp;1001</td>
<td><a rel="nofollow" href="http://zh.wikipedia.org/wiki/9" title="9">9</a></td>
<td>09</td>
<td><a rel="nofollow" href="http://zh.wikipedia.org/wiki/HT" title="HT" class="mw-disambig">HT</a></td>
<td>␉</td>
<td>^I</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E6%B0%B4%E5%B9%B3&amp;action=edit&amp;redlink=1" class="new" title="水平（页面不存在）">水平</a><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E5%AE%9A%E4%BD%8D%E7%AC%A6%E8%99%9F&amp;action=edit&amp;redlink=1" class="new" title="定位符号（页面不存在）">定位符号</a></td>
</tr>
<tr>
<td>0000&nbsp;1010</td>
<td><a rel="nofollow" href="http://zh.wikipedia.org/wiki/10" title="10">10</a></td>
<td>0A</td>
<td><a rel="nofollow" href="http://zh.wikipedia.org/wiki/LF" title="LF" class="mw-redirect">LF</a></td>
<td>␊</td>
<td>^J</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E6%8F%9B%E8%A1%8C" title="换行">换行键</a></td>
</tr>
<tr>
<td>0000&nbsp;1011</td>
<td><a rel="nofollow" href="http://zh.wikipedia.org/wiki/11" title="11">11</a></td>
<td>0B</td>
<td><a rel="nofollow" href="http://zh.wikipedia.org/wiki/VT" title="VT" class="mw-disambig">VT</a></td>
<td>␋</td>
<td>^K</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E5%9E%82%E7%9B%B4" title="垂直">垂直</a><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E5%AE%9A%E4%BD%8D%E7%AC%A6%E8%99%9F&amp;action=edit&amp;redlink=1" class="new" title="定位符号（页面不存在）">定位符号</a></td>
</tr>
<tr>
<td>0000&nbsp;1100</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/12" title="12">12</a></td>
<td align="center">0C</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/FF" title="FF" class="mw-disambig">FF</a></td>
<td align="center" style="font-family:'lucida sans unicode','arial unicode ms'">␌</td>
<td>^L</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E6%8D%A2%E9%A1%B5%E9%94%AE&amp;action=edit&amp;redlink=1" class="new" title="换页键（页面不存在）">换页键</a></td>
</tr>
<tr>
<td>0000&nbsp;1101</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/13" title="13">13</a></td>
<td align="center">0D</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/CR" title="CR" class="mw-disambig">CR</a></td>
<td align="center" style="font-family:'lucida sans unicode','arial unicode ms'">␍</td>
<td>^M</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/Enter%E9%94%AE" title="Enter键" class="mw-redirect">Enter键</a></td>
</tr>
<tr>
<td>0000&nbsp;1110</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/14" title="14">14</a></td>
<td align="center">0E</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/SO" title="SO" class="mw-disambig">SO</a></td>
<td align="center" style="font-family:'lucida sans unicode','arial unicode ms'">␎</td>
<td>^N</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E5%8F%96%E6%B6%88%E8%AE%8A%E6%8D%A2&amp;action=edit&amp;redlink=1" class="new" title="取消变换（页面不存在）">取消变换</a>（Shift out）</td>
</tr>
<tr>
<td>0000&nbsp;1111</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/15" title="15">15</a></td>
<td align="center">0F</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/SI" title="SI" class="mw-redirect">SI</a></td>
<td align="center" style="font-family:'lucida sans unicode','arial unicode ms'">␏</td>
<td>^O</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E5%90%AF%E7%94%A8%E8%AE%8A%E6%8D%A2&amp;action=edit&amp;redlink=1" class="new" title="启用变换（页面不存在）">启用变换</a>（Shift in）</td>
</tr>
<tr>
<td>0001&nbsp;0000</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/16" title="16">16</a></td>
<td align="center">10</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=DLE&amp;action=edit&amp;redlink=1" class="new" title="DLE（页面不存在）">DLE</a></td>
<td align="center" style="font-family:'lucida sans unicode','arial unicode ms'">␐</td>
<td>^P</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E8%B7%B3%E5%87%BA%E6%95%B0%E6%8D%AE%E9%80%9A%E8%AE%AF&amp;action=edit&amp;redlink=1" class="new" title="跳出数据通讯（页面不存在）">跳出数据通讯</a></td>
</tr>
<tr>
<td>0001&nbsp;0001</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/17" title="17">17</a></td>
<td align="center">11</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/DC" title="DC" class="mw-disambig">DC</a>1</td>
<td align="center" style="font-family:'lucida sans unicode','arial unicode ms'">␑</td>
<td>^Q</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E8%A8%AD%E5%82%99%E6%8E%A7%E5%88%B6&amp;action=edit&amp;redlink=1" class="new" title="设备控制（页面不存在）">设备控制</a>一（<a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=XON&amp;action=edit&amp;redlink=1" class="new" title="XON（页面不存在）">XON</a> <a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E5%95%9F%E7%94%A8%E8%BB%9F%E9%AB%94%E9%80%9F%E5%BA%A6%E6%8E%A7%E5%88%B6&amp;action=edit&amp;redlink=1" class="new" title="激活软件速度控制（页面不存在）">激活软件速度控制</a>）</td>
</tr>
<tr>
<td>0001&nbsp;0010</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/18" title="18">18</a></td>
<td align="center">12</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/DC" title="DC" class="mw-disambig">DC</a>2</td>
<td align="center" style="font-family:'lucida sans unicode','arial unicode ms'">␒</td>
<td>^R</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E8%A8%AD%E5%82%99%E6%8E%A7%E5%88%B6&amp;action=edit&amp;redlink=1" class="new" title="设备控制（页面不存在）">设备控制</a>二</td>
</tr>
<tr>
<td>0001&nbsp;0011</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/19" title="19">19</a></td>
<td align="center">13</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/DC" title="DC" class="mw-disambig">DC</a>3</td>
<td align="center" style="font-family:'lucida sans unicode','arial unicode ms'">␓</td>
<td>^S</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E8%A8%AD%E5%82%99%E6%8E%A7%E5%88%B6&amp;action=edit&amp;redlink=1" class="new" title="设备控制（页面不存在）">设备控制</a>三（<a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=XOFF&amp;action=edit&amp;redlink=1" class="new" title="XOFF（页面不存在）">XOFF</a> <a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E5%81%9C%E7%94%A8%E8%BB%9F%E9%AB%94%E9%80%9F%E5%BA%A6%E6%8E%A7%E5%88%B6&amp;action=edit&amp;redlink=1" class="new" title="停用软件速度控制（页面不存在）">停用软件速度控制</a>）</td>
</tr>
<tr>
<td>0001&nbsp;0100</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/20" title="20">20</a></td>
<td align="center">14</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/DC" title="DC" class="mw-disambig">DC</a>4</td>
<td align="center" style="font-family:'lucida sans unicode','arial unicode ms'">␔</td>
<td>^T</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E8%A8%AD%E5%82%99%E6%8E%A7%E5%88%B6&amp;action=edit&amp;redlink=1" class="new" title="设备控制（页面不存在）">设备控制</a>四</td>
</tr>
<tr>
<td>0001&nbsp;0101</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/21" title="21">21</a></td>
<td align="center">15</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=NAK&amp;action=edit&amp;redlink=1" class="new" title="NAK（页面不存在）">NAK</a></td>
<td align="center" style="font-family:'lucida sans unicode','arial unicode ms'">␕</td>
<td>^U</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E7%A2%BA%E8%AA%8D%E5%A4%B1%E6%95%97%E5%9B%9E%E6%87%89&amp;action=edit&amp;redlink=1" class="new" title="确认失败回应（页面不存在）">确认失败回应</a></td>
</tr>
<tr>
<td>0001&nbsp;0110</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/22" title="22">22</a></td>
<td align="center">16</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=SYN&amp;action=edit&amp;redlink=1" class="new" title="SYN（页面不存在）">SYN</a></td>
<td align="center" style="font-family:'lucida sans unicode','arial unicode ms'">␖</td>
<td>^V</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E5%90%8C%E6%AD%A5%E7%94%A8%E6%9A%AB%E5%81%9C&amp;action=edit&amp;redlink=1" class="new" title="同步用暂停（页面不存在）">同步用暂停</a></td>
</tr>
<tr>
<td>0001&nbsp;0111</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/23" title="23">23</a></td>
<td align="center">17</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=ETB&amp;action=edit&amp;redlink=1" class="new" title="ETB（页面不存在）">ETB</a></td>
<td align="center" style="font-family:'lucida sans unicode','arial unicode ms'">␗</td>
<td>^W</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E5%8D%80%E5%A1%8A%E5%82%B3%E8%BC%B8%E7%BB%93%E6%9D%9F&amp;action=edit&amp;redlink=1" class="new" title="区块传输结束（页面不存在）">区块传输结束</a></td>
</tr>
<tr>
<td>0001&nbsp;1000</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/24" title="24">24</a></td>
<td align="center">18</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/CAN" title="CAN" class="mw-disambig">CAN</a></td>
<td align="center" style="font-family:'lucida sans unicode','arial unicode ms'">␘</td>
<td>^X</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E5%8F%96%E6%B6%88&amp;action=edit&amp;redlink=1" class="new" title="取消（页面不存在）">取消</a></td>
</tr>
<tr>
<td>0001&nbsp;1001</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/25" title="25">25</a></td>
<td align="center">19</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/EM" title="EM" class="mw-disambig">EM</a></td>
<td align="center" style="font-family:'lucida sans unicode','arial unicode ms'">␙</td>
<td>^Y</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E9%80%A3%E7%B7%9A%E4%BB%8B%E8%B4%A8%E4%B8%AD%E6%96%AD&amp;action=edit&amp;redlink=1" class="new" title="连接介质中断（页面不存在）">连接介质中断</a></td>
</tr>
<tr>
<td>0001&nbsp;1010</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/26" title="26">26</a></td>
<td align="center">1A</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=SUB&amp;action=edit&amp;redlink=1" class="new" title="SUB（页面不存在）">SUB</a></td>
<td align="center" style="font-family:'lucida sans unicode','arial unicode ms'">␚</td>
<td>^Z</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E6%9B%BF%E6%8F%9B&amp;action=edit&amp;redlink=1" class="new" title="替换（页面不存在）">替换</a></td>
</tr>
<tr>
<td>0001&nbsp;1011</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/27" title="27">27</a></td>
<td align="center">1B</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/ESC" title="ESC" class="mw-disambig">ESC</a></td>
<td align="center" style="font-family:'lucida sans unicode','arial unicode ms'">␛</td>
<td>^[</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E9%80%80%E5%87%BA%E9%94%AE" title="退出键">退出键</a></td>
</tr>
<tr>
<td>0001&nbsp;1100</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/28" title="28">28</a></td>
<td align="center">1C</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/FS" title="FS" class="mw-redirect">FS</a></td>
<td align="center" style="font-family:'lucida sans unicode','arial unicode ms'">␜</td>
<td>^\</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E6%96%87%E4%BB%B6%E5%88%86%E5%89%B2%E7%AC%A6&amp;action=edit&amp;redlink=1" class="new" title="文件分区符（页面不存在）">文件分区符</a></td>
</tr>
<tr>
<td>0001&nbsp;1101</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/29" title="29">29</a></td>
<td align="center">1D</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/GS" title="GS" class="mw-disambig">GS</a></td>
<td align="center" style="font-family:'lucida sans unicode','arial unicode ms'">␝</td>
<td>^]</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E7%BE%A4%E7%B5%84%E5%88%86%E9%9A%94%E7%AC%A6&amp;action=edit&amp;redlink=1" class="new" title="组群分隔符（页面不存在）">组群分隔符</a></td>
</tr>
<tr>
<td>0001&nbsp;1110</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/30" title="30">30</a></td>
<td align="center">1E</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/RS" title="RS" class="mw-disambig">RS</a></td>
<td align="center" style="font-family:'lucida sans unicode','arial unicode ms'">␞</td>
<td>^^</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E8%AE%B0%E5%BD%95%E5%88%86%E9%9A%94%E7%AC%A6&amp;action=edit&amp;redlink=1" class="new" title="记录分隔符（页面不存在）">记录分隔符</a></td>
</tr>
<tr>
<td>0001&nbsp;1111</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/31" title="31">31</a></td>
<td align="center">1F</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/US" title="US" class="mw-redirect">US</a></td>
<td align="center" style="font-family:'lucida sans unicode','arial unicode ms'">␟</td>
<td>^_</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/w/index.php?title=%E5%8D%95%E5%85%83%E5%88%86%E9%9A%94%E7%AC%A6&amp;action=edit&amp;redlink=1" class="new" title="单元分隔符（页面不存在）">单元分隔符</a></td>
</tr>
<tr>
<td colspan="7"></td>
</tr>
<tr>
<td>0111&nbsp;1111</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/127" title="127">127</a></td>
<td align="center">7F</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/DEL" title="DEL" class="mw-redirect">DEL</a></td>
<td align="center" style="font-family:'lucida sans unicode','arial unicode ms'">␡</td>
<td>^?</td>
<td style="text-align:left"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E5%88%AA%E9%99%A4" title="删除">删除</a></td>
</tr>
</tbody></table>

<table border="1" cellspacing="0" cellpadding="2" class="wikitable" style="float: left;">
<tbody><tr valign="bottom">
<th><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E4%BA%8C%E8%BF%9B%E5%88%B6" title="二进制">二进制</a></th>
<th><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E5%8D%81%E8%BF%9B%E5%88%B6" title="十进制">十进制</a></th>
<th><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E5%8D%81%E5%85%AD%E8%BF%9B%E5%88%B6" title="十六进制">十六进制</a></th>
<th><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E5%9B%BE%E5%BD%A2" title="图形">图形</a></th>
</tr>
<tr>
<td>0010&nbsp;0000</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/32" title="32">32</a></td>
<td align="center">20</td>
<td align="center" style="white-space:nowrap;">(<a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E7%A9%BA%E6%A0%BC" title="空格">space</a>)</td>
</tr>
<tr>
<td>0010&nbsp;0001</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/33" title="33">33</a></td>
<td align="center">21</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E6%83%8A%E5%8F%B9%E5%8F%B7" title="惊叹号" class="mw-redirect">!</a></td>
</tr>
<tr>
<td>0010&nbsp;0010</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/34" title="34">34</a></td>
<td align="center">22</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E5%8F%8C%E5%BC%95%E5%8F%B7" title="双引号" class="mw-redirect">"</a></td>
</tr>
<tr>
<td>0010&nbsp;0011</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/35" title="35">35</a></td>
<td align="center">23</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E4%BA%95%E8%99%9F" title="井号">#</a></td>
</tr>
<tr>
<td>0010&nbsp;0100</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/36" title="36">36</a></td>
<td align="center">24</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/$" title="$" class="mw-disambig">$</a></td>
</tr>
<tr>
<td>0010&nbsp;0101</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/37" title="37">37</a></td>
<td align="center">25</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E7%99%BE%E5%88%86%E6%AF%94" title="百分比">%</a></td>
</tr>
<tr>
<td>0010&nbsp;0110</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/38" title="38">38</a></td>
<td align="center">26</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%26" title="&amp;">&amp;</a></td>
</tr>
<tr>
<td>0010&nbsp;0111</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/39" title="39">39</a></td>
<td align="center">27</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E5%8D%95%E5%BC%95%E5%8F%B7" title="单引号" class="mw-redirect">'</a></td>
</tr>
<tr>
<td>0010&nbsp;1000</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/40" title="40">40</a></td>
<td align="center">28</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E6%8B%AC%E8%99%9F" title="括号" class="mw-redirect">(</a></td>
</tr>
<tr>
<td>0010&nbsp;1001</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/41" title="41">41</a></td>
<td align="center">29</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E6%8B%AC%E8%99%9F" title="括号" class="mw-redirect">)</a></td>
</tr>
<tr>
<td>0010&nbsp;1010</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/42" title="42">42</a></td>
<td align="center">2A</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E6%98%9F%E5%8F%B7" title="星号" class="mw-redirect">*</a></td>
</tr>
<tr>
<td>0010&nbsp;1011</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/43" title="43">43</a></td>
<td align="center">2B</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E5%8A%A0%E5%8F%B7" title="加号" class="mw-redirect">+</a></td>
</tr>
<tr>
<td>0010&nbsp;1100</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/44" title="44">44</a></td>
<td align="center">2C</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E9%80%97%E5%8F%B7" title="逗号" class="mw-redirect">,</a></td>
</tr>
<tr>
<td>0010&nbsp;1101</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/45" title="45">45</a></td>
<td align="center">2D</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E5%87%8F%E5%8F%B7" title="减号" class="mw-redirect">-</a></td>
</tr>
<tr>
<td>0010&nbsp;1110</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/46" title="46">46</a></td>
<td align="center">2E</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E5%8F%A5%E7%82%B9" title="句点" class="mw-redirect">.</a></td>
</tr>
<tr>
<td>0010&nbsp;1111</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/47" title="47">47</a></td>
<td align="center">2F</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E6%96%9C%E7%B7%9A" title="斜线">/</a></td>
</tr>
<tr>
<td>0011&nbsp;0000</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/48" title="48">48</a></td>
<td align="center">30</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/0" title="0">0</a></td>
</tr>
<tr>
<td>0011&nbsp;0001</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/49" title="49">49</a></td>
<td align="center">31</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/1" title="1">1</a></td>
</tr>
<tr>
<td>0011&nbsp;0010</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/50" title="50">50</a></td>
<td align="center">32</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/2" title="2">2</a></td>
</tr>
<tr>
<td>0011&nbsp;0011</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/51" title="51">51</a></td>
<td align="center">33</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/3" title="3">3</a></td>
</tr>
<tr>
<td>0011&nbsp;0100</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/52" title="52">52</a></td>
<td align="center">34</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/4" title="4">4</a></td>
</tr>
<tr>
<td>0011&nbsp;0101</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/53" title="53">53</a></td>
<td align="center">35</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/5" title="5">5</a></td>
</tr>
<tr>
<td>0011&nbsp;0110</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/54" title="54">54</a></td>
<td align="center">36</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/6" title="6">6</a></td>
</tr>
<tr>
<td>0011&nbsp;0111</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/55" title="55">55</a></td>
<td align="center">37</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/7" title="7">7</a></td>
</tr>
<tr>
<td>0011&nbsp;1000</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/56" title="56">56</a></td>
<td align="center">38</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/8" title="8">8</a></td>
</tr>
<tr>
<td>0011&nbsp;1001</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/57" title="57">57</a></td>
<td align="center">39</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/9" title="9">9</a></td>
</tr>
<tr>
<td>0011&nbsp;1010</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/58" title="58">58</a></td>
<td align="center">3A</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E5%86%92%E5%8F%B7" title="冒号">:</a></td>
</tr>
<tr>
<td>0011&nbsp;1011</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/59" title="59">59</a></td>
<td align="center">3B</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E5%88%86%E5%8F%B7" title="分号" class="mw-redirect">;</a></td>
</tr>
<tr>
<td>0011&nbsp;1100</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/60" title="60">60</a></td>
<td align="center">3C</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E5%B0%8F%E6%96%BC%E8%99%9F" title="小于号" class="mw-redirect">&lt;</a></td>
</tr>
<tr>
<td>0011&nbsp;1101</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/61" title="61">61</a></td>
<td align="center">3D</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E7%AD%89%E5%8F%B7" title="等号">=</a></td>
</tr>
<tr>
<td>0011&nbsp;1110</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/62" title="62">62</a></td>
<td align="center">3E</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E5%A4%A7%E6%96%BC%E8%99%9F" title="大于号" class="mw-redirect">&gt;</a></td>
</tr>
<tr>
<td>0011&nbsp;1111</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/63" title="63">63</a></td>
<td align="center">3F</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E9%97%AE%E5%8F%B7" title="问号">?</a></td>
</tr>
</tbody></table>

<table border="1" cellspacing="0" cellpadding="2" class="wikitable" style="float: left;">
<tbody><tr valign="bottom">
<th><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E4%BA%8C%E8%BF%9B%E5%88%B6" title="二进制">二进制</a></th>
<th><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E5%8D%81%E8%BF%9B%E5%88%B6" title="十进制">十进制</a></th>
<th><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E5%8D%81%E5%85%AD%E8%BF%9B%E5%88%B6" title="十六进制">十六进制</a></th>
<th><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E5%9B%BE%E5%BD%A2" title="图形">图形</a></th>
</tr>
<tr>
<td>0100&nbsp;0000</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/64" title="64">64</a></td>
<td align="center">40</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/@" title="@">@</a></td>
</tr>
<tr>
<td>0100&nbsp;0001</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/65" title="65">65</a></td>
<td align="center">41</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/A" title="A">A</a></td>
</tr>
<tr>
<td>0100&nbsp;0010</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/66" title="66">66</a></td>
<td align="center">42</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/B" title="B">B</a></td>
</tr>
<tr>
<td>0100&nbsp;0011</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/67" title="67">67</a></td>
<td align="center">43</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/C" title="C">C</a></td>
</tr>
<tr>
<td>0100&nbsp;0100</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/68" title="68">68</a></td>
<td align="center">44</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/D" title="D">D</a></td>
</tr>
<tr>
<td>0100&nbsp;0101</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/69" title="69">69</a></td>
<td align="center">45</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/E" title="E">E</a></td>
</tr>
<tr>
<td>0100&nbsp;0110</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/70" title="70">70</a></td>
<td align="center">46</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/F" title="F">F</a></td>
</tr>
<tr>
<td>0100&nbsp;0111</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/71" title="71">71</a></td>
<td align="center">47</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/G" title="G">G</a></td>
</tr>
<tr>
<td>0100&nbsp;1000</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/72" title="72">72</a></td>
<td align="center">48</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/H" title="H" class="mw-redirect">H</a></td>
</tr>
<tr>
<td>0100&nbsp;1001</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/73" title="73">73</a></td>
<td align="center">49</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/I" title="I">I</a></td>
</tr>
<tr>
<td>0100&nbsp;1010</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/74" title="74">74</a></td>
<td align="center">4A</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/J" title="J">J</a></td>
</tr>
<tr>
<td>0100&nbsp;1011</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/75" title="75">75</a></td>
<td align="center">4B</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/K" title="K">K</a></td>
</tr>
<tr>
<td>0100&nbsp;1100</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/76" title="76">76</a></td>
<td align="center">4C</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/L" title="L">L</a></td>
</tr>
<tr>
<td>0100&nbsp;1101</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/77" title="77">77</a></td>
<td align="center">4D</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/M" title="M">M</a></td>
</tr>
<tr>
<td>0100&nbsp;1110</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/78" title="78">78</a></td>
<td align="center">4E</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/N" title="N">N</a></td>
</tr>
<tr>
<td>0100&nbsp;1111</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/79" title="79">79</a></td>
<td align="center">4F</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/O" title="O">O</a></td>
</tr>
<tr>
<td>0101&nbsp;0000</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/80" title="80">80</a></td>
<td align="center">50</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/P" title="P">P</a></td>
</tr>
<tr>
<td>0101&nbsp;0001</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/81" title="81">81</a></td>
<td align="center">51</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/Q" title="Q">Q</a></td>
</tr>
<tr>
<td>0101&nbsp;0010</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/82" title="82">82</a></td>
<td align="center">52</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/R" title="R">R</a></td>
</tr>
<tr>
<td>0101&nbsp;0011</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/83" title="83">83</a></td>
<td align="center">53</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/S" title="S">S</a></td>
</tr>
<tr>
<td>0101&nbsp;0100</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/84" title="84">84</a></td>
<td align="center">54</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/T" title="T">T</a></td>
</tr>
<tr>
<td>0101&nbsp;0101</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/85" title="85">85</a></td>
<td align="center">55</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/U" title="U">U</a></td>
</tr>
<tr>
<td>0101&nbsp;0110</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/86" title="86">86</a></td>
<td align="center">56</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/V" title="V">V</a></td>
</tr>
<tr>
<td>0101&nbsp;0111</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/87" title="87">87</a></td>
<td align="center">57</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/W" title="W">W</a></td>
</tr>
<tr>
<td>0101&nbsp;1000</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/88" title="88">88</a></td>
<td align="center">58</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/X" title="X">X</a></td>
</tr>
<tr>
<td>0101&nbsp;1001</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/89" title="89">89</a></td>
<td align="center">59</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/Y" title="Y">Y</a></td>
</tr>
<tr>
<td>0101&nbsp;1010</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/90" title="90">90</a></td>
<td align="center">5A</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/Z" title="Z">Z</a></td>
</tr>
<tr>
<td>0101&nbsp;1011</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/91" title="91">91</a></td>
<td align="center">5B</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E6%8B%AC%E8%99%9F" title="括号" class="mw-redirect">[</a></td>
</tr>
<tr>
<td>0101&nbsp;1100</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/92" title="92">92</a></td>
<td align="center">5C</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E5%8F%8D%E6%96%9C%E7%BA%BF" title="反斜线">\</a></td>
</tr>
<tr>
<td>0101&nbsp;1101</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/93" title="93">93</a></td>
<td align="center">5D</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E6%8B%AC%E8%99%9F" title="括号" class="mw-redirect">]</a></td>
</tr>
<tr>
<td>0101&nbsp;1110</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/94" title="94">94</a></td>
<td align="center">5E</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%5E" title="^" class="mw-redirect">^</a></td>
</tr>
<tr>
<td>0101&nbsp;1111</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/95" title="95">95</a></td>
<td align="center">5F</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E5%BA%95%E7%B7%9A" title="下划线" class="mw-redirect">_</a></td>
</tr>
</tbody></table>

<table border="1" cellspacing="0" cellpadding="2" class="wikitable" style="float: left;">
<tbody><tr valign="bottom">
<th><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E4%BA%8C%E8%BF%9B%E5%88%B6" title="二进制">二进制</a></th>
<th><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E5%8D%81%E8%BF%9B%E5%88%B6" title="十进制">十进制</a></th>
<th><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E5%8D%81%E5%85%AD%E8%BF%9B%E5%88%B6" title="十六进制">十六进制</a></th>
<th><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E5%9B%BE%E5%BD%A2" title="图形">图形</a></th>
</tr>
<tr>
<td>0110&nbsp;0000</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/96" title="96">96</a></td>
<td align="center">60</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E9%87%8D%E9%9F%B3%E7%AC%A6" title="重音符">`</a></td>
</tr>
<tr>
<td>0110&nbsp;0001</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/97" title="97">97</a></td>
<td align="center">61</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/A" title="A">a</a></td>
</tr>
<tr>
<td>0110&nbsp;0010</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/98" title="98">98</a></td>
<td align="center">62</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/B" title="B">b</a></td>
</tr>
<tr>
<td>0110&nbsp;0011</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/99" title="99">99</a></td>
<td align="center">63</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/C" title="C">c</a></td>
</tr>
<tr>
<td>0110&nbsp;0100</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/100" title="100">100</a></td>
<td align="center">64</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/D" title="D">d</a></td>
</tr>
<tr>
<td>0110&nbsp;0101</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/101" title="101">101</a></td>
<td align="center">65</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/E" title="E">e</a></td>
</tr>
<tr>
<td>0110&nbsp;0110</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/102" title="102">102</a></td>
<td align="center">66</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/F" title="F">f</a></td>
</tr>
<tr>
<td>0110&nbsp;0111</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/103" title="103">103</a></td>
<td align="center">67</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/G" title="G">g</a></td>
</tr>
<tr>
<td>0110&nbsp;1000</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/104" title="104">104</a></td>
<td align="center">68</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/H" title="H" class="mw-redirect">h</a></td>
</tr>
<tr>
<td>0110&nbsp;1001</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/105" title="105">105</a></td>
<td align="center">69</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/I" title="I">i</a></td>
</tr>
<tr>
<td>0110&nbsp;1010</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/106" title="106">106</a></td>
<td align="center">6A</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/J" title="J">j</a></td>
</tr>
<tr>
<td>0110&nbsp;1011</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/107" title="107">107</a></td>
<td align="center">6B</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/K" title="K">k</a></td>
</tr>
<tr>
<td>0110&nbsp;1100</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/108" title="108">108</a></td>
<td align="center">6C</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/L" title="L">l</a></td>
</tr>
<tr>
<td>0110&nbsp;1101</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/109" title="109">109</a></td>
<td align="center">6D</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/M" title="M">m</a></td>
</tr>
<tr>
<td>0110&nbsp;1110</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/110" title="110">110</a></td>
<td align="center">6E</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/N" title="N">n</a></td>
</tr>
<tr>
<td>0110&nbsp;1111</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/111" title="111">111</a></td>
<td align="center">6F</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/O" title="O">o</a></td>
</tr>
<tr>
<td>0111&nbsp;0000</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/112" title="112">112</a></td>
<td align="center">70</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/P" title="P">p</a></td>
</tr>
<tr>
<td>0111&nbsp;0001</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/113" title="113">113</a></td>
<td align="center">71</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/Q" title="Q">q</a></td>
</tr>
<tr>
<td>0111&nbsp;0010</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/114" title="114">114</a></td>
<td align="center">72</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/R" title="R">r</a></td>
</tr>
<tr>
<td>0111&nbsp;0011</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/115" title="115">115</a></td>
<td align="center">73</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/S" title="S">s</a></td>
</tr>
<tr>
<td>0111&nbsp;0100</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/116" title="116">116</a></td>
<td align="center">74</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/T" title="T">t</a></td>
</tr>
<tr>
<td>0111&nbsp;0101</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/117" title="117">117</a></td>
<td align="center">75</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/U" title="U">u</a></td>
</tr>
<tr>
<td>0111&nbsp;0110</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/118" title="118">118</a></td>
<td align="center">76</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/V" title="V">v</a></td>
</tr>
<tr>
<td>0111&nbsp;0111</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/119" title="119">119</a></td>
<td align="center">77</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/W" title="W">w</a></td>
</tr>
<tr>
<td>0111&nbsp;1000</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/120" title="120">120</a></td>
<td align="center">78</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/X" title="X">x</a></td>
</tr>
<tr>
<td>0111&nbsp;1001</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/121" title="121">121</a></td>
<td align="center">79</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/Y" title="Y">y</a></td>
</tr>
<tr>
<td>0111&nbsp;1010</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/122" title="122">122</a></td>
<td align="center">7A</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/Z" title="Z">z</a></td>
</tr>
<tr>
<td>0111&nbsp;1011</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/123" title="123">123</a></td>
<td align="center">7B</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E6%8B%AC%E8%99%9F" title="括号" class="mw-redirect">{</a></td>
</tr>
<tr>
<td>0111&nbsp;1100</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/124" title="124">124</a></td>
<td align="center">7C</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E8%B1%8E%E7%B7%9A" title="竖线">|</a></td>
</tr>
<tr>
<td>0111&nbsp;1101</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/125" title="125">125</a></td>
<td align="center">7D</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E6%8B%AC%E8%99%9F" title="括号" class="mw-redirect">}</a></td>
</tr>
<tr>
<td>0111&nbsp;1110</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/126" title="126">126</a></td>
<td align="center">7E</td>
<td align="center"><a rel="nofollow" href="http://zh.wikipedia.org/wiki/%E6%B3%A2%E6%B5%AA%E8%99%9F" title="波浪号">~</a></td>
</tr>
</tbody></table>

<br/>

我们会发现，这张表上的字符比较全，比我们刚刚 <a href="" title="课堂作业③">自己定义的规则</a> 要详细很多，并且多了很多不知道作用的字符。由于这张表流传最广，基本上现代的计算机都支持按照这张表的规则来存储字符。所以，我们在学习计算机编程的过程中往往要跟这张表来打交道。

<font color="blue">【课堂作业④】</font>要熟悉这张表也很简单，大家尝试根据上面这张表把文字 
[code]
Alan: How old are you, Bob?
Bob: I am 18.
[/code]
存储在计算机中的值写出来（转成数字）看看。这个做完之后，再尝试把数字转成二进制看看（拓展作业）。

<h1>与我定下契约吧，少年</h1>

现在，让我们来看一个现象。根据课堂作业①和④，我们发现数字 65 存储在内存的时候（即二进制形式）为 <font color="blue">1000001</font>；而字符 A 存储在内存中的时候，根据ASCII码表我们可以查到其是以数字65来存储的，也就是说字符 A 在内存中的形式和数字 65 一样的，都是 <font color="blue">1000001</font>。

<font size="20px">那么问题来了。</font>

你现在正在盯着电脑屏幕看教程，对，没错，就是你现在正在盯着看的这台电脑。博主的电脑内存是4G的，你的电脑内存是几G的？

<font color="blue">【思考题①】</font>噢啦，重点不是这个问题，而是如果如果你能直接看到内存上数据的内容，你要怎么确定这块数据表达的是什么。比如当你在内存上看到 <font color="blue">1000001</font> 的时候，你觉得这段数据到底表示的是数值的 65、字符的 A 或者是其他答案？

<font color="blue">【思考题②】</font>如果上述问题你考虑清楚之后，请设想一个解决方案来处理这个让人迷惑的数据含义问题。

这两个问题非常重要，如果你想清楚的话，会对整个编程体系有更加深刻的理解。据 Lellansin 说对于新人而言，这个问题的思考时间与其智商成正比。希望各位看到这里停下来好好思考一下。

请在下方填入你的IQ值，程序会自动根据你的IQ来倒计时，倒计时结束后会自动显示下一段内容。

你的IQ是【____】<button>开始思考</button>


那么看到这里，相信你已经有认真思考过了。

首先<font color="blue">【思考题①】</font>正确的答案是，不管是谁，仅仅只是看到这样一段二进制的数据，哪怕是C语言之父、黑客之神齐聚一堂都不能“确认”这段二进制的数据到底要表达什么。因为它可以是数值、可以是字符甚至可以是汇编机器码等等。

接着<font color="blue">【思考题②】</font>解决方案是四个字：数据类型。


<h1>数据类型</h1>

数据类型是什么？为什么我们要数据类型？

数据类型是一种对内存上数据存储、读写的一种约定。

我们虽然没有办法根据数据直接知道其含义，但是我们可以按照约定的类型来处理数据。也就是说，在面对 <font color="blue">1000001</font> 的时候，如果我们按照数值的类型来读写它，那么它就是一个数值，如果我们按照字符的类型的读写它，那么它就是一个字符。

其所表达的含义不在于其本身，而在于我们使用什么样的规则和约定来处理它。

<font color="red">就好像我们开始所做的，定义一个规则把文字转成数字一样。重要并不是那些数据，而是我们自己约定的规则。</font>

那么数据类型到底从哪些方面做了约定？

<h2>1.获取该类型的数据 <font color="grey">(读 read)</font></h2>

数据类型约定好了，不同的类型按照什么样的方式来读取数据。

同样一个二进制数据 <font color="blue">1000001</font>，当你使用<font color="blue">整数</font>类型来读取的时候其值为 65，当你使用<font color="blue">小数</font>类型来读取的时候其值为 65.0，当你使用字符类型来读取的时候其值为 A

<h2>2.修改该类型的数据 <font color="grey">(写 write)</font></h2>

数据类型约定好了，不同的类型按照什么样的方式来写入数据。

比如对于一个<font color="blue">整数</font>类型的数据，当你要往其中写入 如 1.2 这样的<font color="blue">小数</font>时，其最终只会得到结果 1 并舍弃<font color="blue">小数</font>，因为<font color="blue">整数</font>类型只能保存<font color="blue">整数</font>，这是约定好的。

<h2>3.空间大小 <font color="grey">(size)</font></h2>

数据类型约定好了，不同的类型的数据其所占的空间大小。

比如我们开始做【课堂作业①】用数字表示文字的时候的如下例子：
[code]
91215225251521
[/code]
大家在做过【课堂作业③】之后也会理解，有的时候中间的数字会改变，规则列表也会改变。所以可想而知，这些数据存在计算机中的时候，互相之间都会留空。例如这样存：
[code]
0009 0012 0015 0022 0005 0025 0015 0021
[/code]
这样当中间某些数据变化的时候，内存中也有足够的空间应对。至于这个“足够的空间”到底是多大，具体就是由数据类型来约定。
