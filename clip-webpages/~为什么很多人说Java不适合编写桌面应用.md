---
created: 2024-08-02T12:00:00
source: https://www.zhihu.com/question/19711713
type: archive-web
modified: 2025-01-15T11:38:16
---

这事还得从 Java 的传统，“跨平台一致性”说起。

在写后台逻辑的时候，跨平台是好东西。很多公司都是在 Windows 下开发，在 Linux 下部署，方便。

但**涉及到 GUI 的时候，跨平台就成了个“看上去很美”的东西**。理论上，我写个窗口，在 Windows 和 Mac 下都一样能用，那是多么美好的事啊。但实际上，每个平台提供的 GUI 控件多多少少有点差别，一坚持跨平台，麻烦就来了，该支持多少控件，怎么支持呢。

一开始，Java 的思路是：那简单啊，有原生控件干嘛不用，至于不跨平台的，就不支持呗，又坚持了原则，又回避了问题。这一代的 gui 库，**awt**，就此诞生。

因为 Java 一开始是一根筋想推广 Applet 的，只是“顺便”也支持本地应用，设计成这样不能说不合适，毕竟，HTML 也是同样的思路，只支持几种最基本的控件。

但对于想开发复杂点界面的人来说，就有麻烦了。想来个目录树吧，对不起，不支持；想来个进度条吧，对不起，不支持。旁边放着 Delphi 和 VB 这么方便的东西，哥干吗受这气啊。

这样一来，Java 自己也觉得说不过去了。但又要跨平台，又要提供丰富的控件支持，那就只有另起炉灶，开始用第二种思路：自己动手、丰衣足食，自己重写一套 GUI 控件，代替操作系统的原生控件。这一代的 gui 库，叫做**swing**。

这也是一个想“彻底”解决问题的思路，但是要付出代价。

代价之一就是效率。我们可以参考一下另一个相同思路的产品——flash。为了实现矢量动画，在 flash 的那个小框里，图是一帧一帧地算出来的。接下来的事情我们都知道了：复杂的 flash 动画极耗 cpu；iPhone 说，您太耗电了，俺就不支持了；Adobe 说，那好吧，那俺也不费心折腾移动版 flash 了。

自己画出来的控件毕竟不能跟原生控件比效率，尤其是在早期 Java 优化还不够完善的时候。而且，自力更生的目的只是为了平台兼容，不是为了更好的效果，这事儿其实怎么想怎么亏。

代价之二就是效果。自己画的控件毕竟只是模拟，还是会有细节差别。比如著名的**毛玻璃效果**，这不是简单套样式就能套出来的。

而且，各个平台控件的风格本来就不一样，虽然 swing 提供了几种外观，但大部分程序出于偷懒或是跨平台一致考虑，还是使用默认外观。默认外观跟平台不一致倒也不是问题，主要是别比平台效果土。我用着 win7，一个程序非让我感觉回到 xp 时代，心里特别添堵。

就这样，一帮人商量着，又琢磨出个新思路：做适配。平台有这个控件，就直接用，保证效率；没有，再造轮子，保证可用。就这样，**swt**问世。eclipse 的 gui 就是基于此。

swt 是赞，不过这属于改良，两个根本问题仍在：

  - 1. 跟操作系统 api 打交道不是 Java 的长项，效率仍然不能与 c++ 等相提并论。
  - 2. 到底要不要跨平台。如果要跨平台，swt 接浏览器控件、接 ActiveX 控件的功能就成了形同虚设；而要是不想跨平台，又何必使用 Java 呢，.Net 在一旁已经恭候多时了。

> @冯东：另一方面，即使每个平台都支持的 control 也多多少少有些差异。比如同样是文本框，Windows 和 Mac (Cocoa) 对待 non-English 输入法选词的语义就不同。再比如对 focus-lost 的处理二者也不同。所以 SWT 其实目前很难做到 Swing 那样的跨平台。**跨平台么，终究还是只能做到最大公约数**，比如 x86 支持 4 级，Unix 只用两级。可那是大家都同意不用的。在 UI 级别可没有人能同意不用操作系统的某个功能。

除了技术本身，还有一个产业的问题，围绕着 GUI 控件也存在一个生态环境，**没有丰富的领域、行业控件的支持，技术本身的战斗力也会大打折扣。而 Java 这方面的生态较为薄弱**。

综上，如果一个 GUI 程序使用 Java，通常都是有这些特征：

  - 确实是想跨平台
  - 对界面并没有太多效果的要求，界面效率也不是瓶颈
  - 相比于其他 GUI 工具，开发人员对 Java 更为熟悉
    - 比如，一些工具的管理界面，很符合
