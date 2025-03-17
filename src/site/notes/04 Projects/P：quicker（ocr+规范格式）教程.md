---
{"dg-publish":true,"dg-permalink":"/notes/quickerocr","permalink":"/notes/quickerocr/","created":"2025-03-17T21:03:55.920+08:00","updated":"2025-03-17T21:57:13.641+08:00"}
---

本文介绍如何使用 quicker 实现快速 ocr+快速格式化文本。并补充一些好用的 quiker 脚本。

## 安装 quiker
quiker 可以把我们在电脑上的一系列操作，打包为一个快捷操作。
比如说，如果我需要对一串文本进行格式规范化，
一般的操作为：找到一个输入框→将英文引号改成中文引号→删除多余空格→把全角字母改成半角字母→删除多余的链接……
但是 quicker 可以把这些操作打包为一个操作：复制文字→点击“规范粘贴”动作。
quiker 仅支持Windows系统；mac 系统有类似的软件，可以自行寻找。
官网地址： https://getquicker.net/
不充钱也能用，只是格子（可安装的动作）比较少，浅度使用足够。
## 如何安装动作
以“截图 ocr ”动作为例：
1. 打开动作网页： https://getquicker.net/Sharedaction?code=ba82e11a-f845-4ca3-44ee-08d690b5076c
2. 点击复制到剪贴板：![Pasted image 20250317210802.png](/img/user/09%20settings/Z%20attachment/Pasted%20image%2020250317210802.png)
3. 鼠标中键唤起 quiker 主界面，找到一个空白的格子，右键，粘贴分享的动作（建议粘在上半部分，因为上半部分是通用的，下半部分是绑定特定应用的）![Pasted image 20250317211458.png|236](/img/user/09%20settings/Z%20attachment/Pasted%20image%2020250317211458.png)
4. 正常情况下，使用只需点击中键唤起quiker 主界面，再点击“截图 ocr ”这个动作的格子，就可以开始截图 ocr，识别后的文字会自动到剪贴板
5. 如果需要更快速的调用，可以开启轮盘菜单，过程如下。
	1. 复制需要放到快捷菜单中的动作
	2. 打开设置（主界面左上角的齿轮）
	3. 将动作粘贴到轮盘菜单中（免费版的格子会比我图中的少一些）
	4. 一般来说，按住鼠标右键不松开，然后向对应方向滑动，即可唤起“截图 ocr ”这个动作

![Pasted image 20250317212118.png](/img/user/09%20settings/Z%20attachment/Pasted%20image%2020250317212118.png)

![Pasted image 20250317211914.png](/img/user/09%20settings/Z%20attachment/Pasted%20image%2020250317211914.png)

在设置中，我们还可以设置唤起主页面和轮盘菜单的方式，如下图
![Pasted image 20250317215306.png](/img/user/09%20settings/Z%20attachment/Pasted%20image%2020250317215306.png)

![Pasted image 20250317215340.png](/img/user/09%20settings/Z%20attachment/Pasted%20image%2020250317215340.png)

## 其他动作推荐
- 推荐配合截图 ocr 使用。
	- [规范粘贴](https://getquicker.net/Sharedaction?code=cfc572a1-47c8-4fab-2457-08d6d7620f1e)：规范来自pdf和某些网页的文字，去除空行空格等。可选择“纯文本粘贴”、“中文规范粘贴”、“英文规范粘贴”三种模式。
		- [规范粘贴纯中文版](https://getquicker.net/Sharedaction?code=6fc45309-7a0a-4763-5368-08d6f4b99472&fromMyShare=true)（不用再进行选择，适合基本只进行中文复制粘贴的场景）：
		- [规范粘贴纯英文版](https://getquicker.net/sharedaction?code=a4f2c372-5d7e-4c6a-47db-08d79838aac0)（不用再进行选择，适合基本只进行英文复制粘贴的场景）：
	- 配合轮盘菜单使用，可实现 左滑一下（截图 ocr）→右滑一下（规范粘贴），30 秒内得到较为规范的 ocr 文字
- 快速搜索类动作：可以一键实现打开某网站，找到搜索栏，输入搜索内容，点击搜索键这一套动作。
	- 通用类
		- [知乎搜索 - by 瓜皮之牙 - 动作信息 - Quicker](https://getquicker.net/Sharedaction?code=ee54db79-b8ce-4175-677b-08d880549e56)
		- [知网搜索 - by 蒺藜 - 动作信息 - Quicker](https://getquicker.net/Sharedaction?code=350b5a6b-c74a-46f9-fa32-08dad9888ab4)
		- [谷歌学术 - by 蒺藜 - 动作信息 - Quicker](https://getquicker.net/Sharedaction?code=7f256c54-bcb2-438f-649c-08dd652533b7)
		- [搜哔哩 - by 瓜皮之牙 - 动作信息 - Quicker](https://getquicker.net/Sharedaction?code=5ee867b0-505e-455c-6776-08d880549e56)
		- [豆瓣搜索 - by huadu - 动作信息 - Quicker](https://getquicker.net/Sharedaction?code=e676b6c1-ddd6-4080-dc74-08d6d447ca05)
	- 语言文字类
		- [查韵典 - by 蒺藜 - 动作信息 - Quicker](https://getquicker.net/Sharedaction?code=f250232c-c762-4395-fa31-08dad9888ab4)
		- [查汉典 - by 蒺藜 - 动作信息 - Quicker](https://getquicker.net/Sharedaction?code=ad3507f9-5d11-43f8-fa34-08dad9888ab4)
		- [数字说文 - by 蒺藜 - 动作信息 - Quicker](https://getquicker.net/Sharedaction?code=cb9c759f-a95b-40d4-fa33-08dad9888ab4)
		- [ctext-先秦兩漢 - by 蒺藜 - 动作信息 - Quicker](https://getquicker.net/Sharedaction?code=c5779fc3-2180-413b-fa35-08dad9888ab4)
		- [GoldenDict - by judgenius - 动作信息 - Quicker](https://getquicker.net/Sharedaction?code=0ff2475a-f714-4a96-66cd-08d710cec307)（需要配合词典软件 goldendict 使用）
- 快速编辑类
	- [剪贴板 - by Cea - 动作信息 - Quicker](https://getquicker.net/Sharedaction?code=9ec53d43-5539-4571-6886-08d8c752bfcb) 保留历史剪贴信息
	- [简繁互换 - by 快客_蚕子 - 动作信息 - Quicker](https://getquicker.net/Sharedaction?code=53190fc1-34c5-4175-ea6c-08d7c0f8387a)
	- [常用语（新版） - by 咿呀杀杀 - 动作信息 - Quicker](https://getquicker.net/Sharedaction?code=1a8e7553-76e9-4527-66d7-08dbaa91cef1) 我用来存很多不同的 ai 提示词
	- [云板 - by 治钧 - 动作信息 - Quicker](https://getquicker.net/Sharedaction?code=66502c1c-6ce0-4edb-37bc-08d8346ce0f2) 用于打草稿
	- 其他动作有兴趣可以自行探索，比如快速加个引号，加个书名号之类，还是很容易实现的
- 其他
	- [Translator - by zryan - 动作信息 - Quicker](https://getquicker.net/Sharedaction?code=04393db9-f4bc-4871-7fb6-08db2506d1ed) 快速翻译
	- [加日期版本号 - by VernonLin - 动作信息 - Quicker](https://getquicker.net/sharedaction?code=2b5d8d44-b318-4bd7-55b3-08d7cbb492a7) 对某文件/文件夹首次使用将添加版本号和当前日期

## 参考教程
想要进一步了解可以参考，以及可以上 b 站搜一些教程
[效率工具「Quicker」的入手指南-01 - 知乎](https://zhuanlan.zhihu.com/p/673926713)
[电脑小白体验 Quicker 软件90天之用后感 - 知乎](https://zhuanlan.zhihu.com/p/305664217)