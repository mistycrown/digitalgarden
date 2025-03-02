---
{"dg-publish":true,"permalink":"/03 pages/101工具应用/url scheme/","created":"2024-11-30T20:43:35.343+08:00","updated":"2025-03-02T20:23:16.878+08:00"}
---

- **什么是URL scheme？**
	- URL scheme是App提供给外部的可以直接操作App的规则。
	- 比如在番茄打卡2.15.1版本提供了一条直接打开任务执行页面的URL scheme。tomatodiary://detail/{taskid}。（提示：番茄打卡中每个任务的taskid可以通过双击任务列表来获得。）
	- 比如微信提供了打开扫一扫的URL scheme。weixin://dl/scan
	- 比如支付宝提供了转账的URL scheme。alipayqr://platformapi/startapp?saId=20000116
	- 比如知乎提供了打开回答页面的URL scheme。zhihu://answers/{id}
	  
	  有很多应用都提供了URL scheme，方便在网页端打开自己的App，或者方便用户使用自己的App。其中URL scheme的前半部分：tomatodiary://可以用来打开App，detail/taskid 后半部分则定义了App会进行什么操作的规则。
- [总结：url scheme 相关 (yuque.com)](https://www.yuque.com/deerain/gannbs/gmkp9w)