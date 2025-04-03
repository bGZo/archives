---
created: 2025-02-24T10:41:53
modified: 2025-03-25T10:05:50
---

## Quartz #done

```json
Plugin.TableOfContents({
	maxDepth: 5,
	minEntries: 1,
	collapseByDefault: true
}),
```

- https://quartz.jzhao.xyz/features/table-of-contents
- https://quartz.jzhao.xyz/plugins/TableOfContents

## [[reading]]

- [中办、国办印发《提振消费专项行动方案》](https://readhub.cn/topic/8hm2uP39lNt)
- [百度 21 亿美元收购 YY 直播](https://readhub.cn/topic/8hGa4XGHR5d)
- [DeepSeek API 充值重启](https://readhub.cn/topic/8hGRptBA68b)
- [知乎放开网页端登录限制，无需登录可直接查看全文](https://readhub.cn/topic/8hGNAJdrkmZ)
- [消息称苹果将重返路由器市场：自研芯片成关键，支持 Wi-Fi 7](https://readhub.cn/topic/8hO1J1K6KdN)
- [荣耀 CEO 李健：未来五年投入超过 100 亿美元建立 AI 生态](https://readhub.cn/topic/8hPCOz323TQ)
- [阿里巴巴技术：ComfyUI：搭积木一样构建专属于自己的AIGC工作流（保姆级教程）](https://tool.lu/article/6Wv/url)
- [使用 Scroll-driven Animations 高效完成滚动动画](https://tool.lu/article/6Wu/url)
- [2 月 CPI 同比下降 0.7%，春节错月等因素影响](https://readhub.cn/topic/8hZq9zoBK2G)
	- [居民消费价格指数（CPI）](https://www.stats.gov.cn/zs/tjws/zytjzbqs/jmxxggzs/202409/t20240910_1956353.html)
- [国家超算互联网平台 QwQ-32B API 接口服务上线，免费提供 100 万 Tokens](https://readhub.cn/topic/8hZrbv0BTOs)
- [这才是真正的用户分层，而不是看平均数](https://tool.lu/article/6Xl/url)
- [古茗技术：前端视角下的图像格式进化论：从像素战争到性能革命](https://tool.lu/article/6Xm/url)
- [阿里巴巴技术：Transformer到底解决什么问题？](https://tool.lu/article/6Xk/url)
- [字节跳动技术：一种基于套餐思想的数据中心建设规划方法](https://tool.lu/article/6Vd/url)
- [腾讯张军否认 AI 搜索植入广告：已经在查，会尽快优化](https://readhub.cn/topic/8h4krAW5dvP)
- [DeepSeek 团队发布注意力新机制新论文，梁文锋是共创之一](https://readhub.cn/topic/8h4rdW7oYqR)
- [微信正灰度测试微信账号系统](https://readhub.cn/topic/8h4vZ2eEdYt)
- [月之暗面 Kimi 暂缓 「烧钱」 投放](https://readhub.cn/topic/8h4nYchIn1B)
- [OpenAI 谋划开源项目](https://readhub.cn/topic/8h4Ny53INQp)
- [百度搜索全量上线 DeepSeek 满血版](https://readhub.cn/topic/8h4KT8pFqHy)
- [百度 2024 年财报：全年营收 1331 亿元 智能云 Q4 同比增长 26%](https://readhub.cn/topic/8h4p7dWGdgv)

## [[macos]]

```shell
# 记录并分享一下 macOS 优化提速脚本 https://www.v2ex.com/t/1117110
# 禁用系统完整性保护(SIP)和认证根卷 - 允许系统级修改，但降低安全性  
csrutil disable  
csrutil authenticated-root disable

# 降低系统安全限制 - 允许未签名应用和禁用代码验证  
sudo nvram boot-args="amfi_allow_any_signature=1 cs_enforcement_disable=1 ipc_control_port_options=0"  
sudo defaults write /Library/Preferences/com.apple.security GKAutoRearm -bool NO  
sudo defaults write /Library/Preferences/com.apple.security.coderequirements Entitlements -string always  
sudo defaults write /Library/Preferences/com.apple.security.coderequirements AllowUnsafeDynamicLinking -bool YES  
sudo defaults write /Library/Preferences/com.apple.security.libraryvalidation.plist DisableLibraryValidation -bool YES

# 禁用应用程序签名验证 - 允许所有来源的应用  
sudo spctl --global-disable

# 防止在网络驱动器上创建.DS_Store 文件  
defaults write com.apple.desktopservices DSDontWriteNetworkStores -bool TRUE

# 查看开机自启动项目录  
open /Library/LaunchDaemons /Library/LaunchAgents ~/Library/LaunchAgents
```

## 如何用 [[mapstruct]] 映射从 A 转换到 B？B 中的某些字段是 A 的属性对象内的值

```java 
@Data
class Child{
	private String childAttr1;
	private String childAttr2;
}
@Data
class A {
	private Long id;
	private Child child; 
}
@Data
class B {
	private Long id;
	private String childAttr1;
	private String childAttr2;
}
```

#### Solution

```java
@Mapper
public interface AConvert {
    AtoBMapper INSTANCE = Mappers.getMapper(AConvert.class);

    @Mapping(source = "child.childAttr1", target = "childAttr1")
    @Mapping(source = "child.childAttr2", target = "childAttr2")
    B toB(A a);
}
```

via: https://stackoverflow.com/questions/50510235/mapstruct-map-nested-object-properties-to-properties

## [[mybatis|Mybatis]] 如何自定义传参名称（2）

第一种方式：

```xml
<!--
List<MeetingDeploy> resultTypeList(List<String> codes);
-->
select * 
from hplan_meeting_deploy where
	meeting_code in
	<foreach item="item" collection="list" open="(" separator="," close=")" index="index">
	      #{item}
	</foreach>
```

第二种方式：

```xml
<!-- 
List<MeetingDeploy> resultTypeList(@Param("codes") List<String> codes);
-->

select * 
from hplan_meeting_deploy where
       meeting_code IN
		<foreach item="item" collection="codes" open="(" separator="," close=")" index="index">
		      #{item}
		</foreach>　　
```

via: https://www.cnblogs.com/wongzzh/p/15019188.html

## 你不需要被拯救

睁眼，又是伸手不见五指、黑隆隆的一天，心理甚至还挂念着昨晚影视剧里的 CP，我已经不记得这究竟是第几次 #循环 了？

每个人都喜欢听故事，我也是。虽然身边有一些朋友已经不再听了，但我多年来仍然保留着这一习惯。我会被他拯救，然后陷入另一种水深火热中。

这本质就是饮鸩止渴，他只会延缓、加重个体的痛苦。但如果追本溯源，痛苦的源头到底是什么？

制度？体制？社会？系统？你是否真正有办法扭动任一这些事务的螺丝？至少我没有。或者说，在这片土地上生活的大部分普通人也都没有。这会造成什么？

我的境遇绝非个体，而是困在整个体统中的人的常态，我们需要一个快速抽离当下的东西，将我们拯救。偶像注定诞生。

但这不应该是问题的解。

## Collections

> 坐标魔都，很多 (数量以千记) 这种一楼沿街商铺，开了一二十年了，在一夜之间成了违法的了，拿砖块给砌上了。
> #beijing
> https://www.v2ex.com/t/1117267#reply12

> 最近在荷兰溜达，搞了两根抽抽，感觉味道一般，比烟还难抽。
> 是这样的，臭的一逼，多抽抽就好了，哥。
> 恭喜你发现了大麻为什么比烟更难上瘾危害比烟小的根本原因
> 一般都是先混在烟里，10 年没碰过这玩意了
> #drug
> https://www.v2ex.com/t/1117406

> 我知道他前妻，当年真的是很知名的博主，中科院博士，微博几百万粉丝。现在按爆出来的八卦，是他逼着前妻退网的，说一家不能有两个人知名，有风险。也是他逼着前妻去了日本，去了俩月离婚，说以后不会再生孩子，父爱都给那一个孩子。结果又找了个生孩子。这些如果都是事实，那这个人就太渣了，前妻也是完全被他 PUA 。
> 王志安我觉得他做采访还可以，但是观点总是走歪，比起某些纯靠编的人有一些看的价值，但是也仅此而已了。
> #Man
> https://www.v2ex.com/t/1117212

> 本来就是从 Netscape 开源而来的非盈利公司，政治正确是 DNA 吧？我有两个同事是 Mozilla 跳来的，感觉他们工资在硅谷算低，很多干活的都是情怀，或者拿着“生计维持费”搞搞他们感兴趣的事情，浏览器优化好像不是这个公司的主业。从这个角度来说，Mozilla 比 Eclipse 基金会已经成功无数倍了，至少拳头产品还有用户群。
>
> 另外它主要收入来源是 Google 给的赞助费，所以作为一个“保护隐私”定位的浏览器默认搜索一直是 Google 而不是 DuckDuckGo ，你就可以看出来他们的底线是不去撼动 Google 。Chrome 是世界上最成功的广告客户端，如果没有广告收入这个动力那最多也就维护成 Safari 那个样子。
>
> 但我也得承认用 Firefox for Android 快 10 年了，几乎没有什么改进，功能很少，而且 bug 也越来越多。如果不是我痛恨 Chromium 内核一家独大我早跳船了。
> #FF
> https://www.v2ex.com/t/1116443

> 荒谬的个人外汇政策
> https://www.v2ex.com/t/1119818

> 读此贴 [中医到底好不好？中医治尿酸有感] ，的有感
> https://www.v2ex.com/t/1119829

> 大早上被叔叔电话问候了
> https://www.v2ex.com/t/1119009