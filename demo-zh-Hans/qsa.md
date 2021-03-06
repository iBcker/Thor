
## 常见问题

### [iOS10 以后证书无法信任]()

iOS10 开始由于系统原因，不能直接跳转到系统设置的二级界面，所以需要手动打开『证书信任』界面开启信任：

`设置 > 通用 > 关于本机 > 证书信任设置`


### [Thor 1.2.2 以后内置筛选器设置]()

Thor 1.2.2 以后实现了更加灵活强大的筛选器配置，可以自己定义并持久化保存。

定义自己的筛选器，生成之前版本的『文本』、『音视频』、『安装包』等内置筛选器时，只用选数据类型相关选项即可，别的条件不用选。


### [如何在过滤器中设置更全面的参数]()

过滤器的目的是为了减少不必要的流量抓取，想要得到更精确的结果就需要灵活使用筛选器（漏斗），得益于 Thor 全实时抓包的优势，可以用筛选器达到过滤器的效果：

`选取过滤器 -> 启动抓包 -> 选择并配置筛选器（漏斗） -> 抓取数据`


### [iOS9 抓包秒断]()

iOS9 越狱机容易出现 Thor 秒断的问题
由于 iOS 的系统限制，NE 扩展类应用最多只允许使用 6MB 的内存，在非越狱系统下基本上 Thor 不会触发此限制。然而在越狱系统下，由于各类插件的插入，会导致 Thor 的内存用量大增，直接无法启动或变得很不稳定。
以下方法可以解除系统的内存限制，让 Thor 能够稳定运行（这将彻底关闭系统内存限制机制，请谨慎）
使用 `iFile` 等文件管理工具，找到`/System/Library/LaunchDaemons/com.apple.jetsamproperties.{Model}.plist` 文件，将其改名为 `.bak`。（如有多个全部要改）

部分设备在越狱后可能会破坏 Thor 的部分权限，导致无法启动，重新安装 Thor 即可解决。

*该段描述照搬自 Surge 相关说明*

<!-- ### [App 中的音视频无法抓取]()

发现有的 App 中无法抓到音视频，这种情况的音视频应该是走的 tcp 流量
目前的解法有两种：

* 找音视频地址的配置，每个音视频要播放前，必然先问服务器要链接地址，这个地址一般是以 json 方式返回
* 去网页版里抓相关视频

比如某视频 App：匹配关键字 ups.yuoku.com,  从响应的 json 中可以找到视频 url -->


<!-- ### [手机上抓到的商店 ipa 为什么不能安装]()

抓 tf 或者 商店 ipa 需要： 新建过滤器，关闭默认的『建议排除域名』

手机商店里抓的ipa为啥安装不了:

1. 要全新安装抓到的才行，更新安装的是增量包，不能装 

2. ipa 有签名，但是没生成帐号验证文件

3. 有高度压缩，要标准化才能安装

4. 因为 2 的原因，安装好以后打开闪退 -->
