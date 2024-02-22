# ExportMD-rectify-pics
## 2024-02-22 update
大家好，由于超级会员token的限制，以及每次导出的最大数量的限制，本项目的批量导出的限制已经越来越多。
由于我个人能力和精力的限制，已无法继续为批量导出markdown项目做深入改进。
好在，很多小伙伴开发了新的导出工具。
大家可以参考这两个基于Node.js的项目，可以较为方便的导出，大家可以按照项目说明自行捣鼓一下。谢谢~


https://github.com/vannvan/yuque-tools


https://github.com/gxr404/yuque-dl


两个新项目的特征如下：
 * 知识库批量导出
 * 无需超级会员
 * 保留大纲的层级结构

## 1、写在前面
![Version](https://img.shields.io/badge/Version-1.0.2-blue) ![License](https://img.shields.io/badge/license-MIT-yellow) ![python](https://img.shields.io/badge/python->=3.6-orange)

简介：ExportMD语雀知识库自动导出为 Markdown 格式，支持同时导出多个知识库。
但ExportMD导出连续三张图片时，会出现错误，只有第一张图片的内容会被识别，本复刻版本增加了正则表达式，修复这一情况

本复刻版本无法提交issue，有问题欢迎到[语雀评论区](https://www.yuque.com/duzh929/blog/ocffqg)和我交流！  

欢迎给我的语雀文档点赞，或者给我复刻的仓库star  

另外我想说明一下，复刻这个仓库的目的是为了防止重要的笔记丢失，让大家能够有一个本地的markdown笔记备份，但我并不希望语雀因此流失用户，语雀真的是一款非常优秀的笔记软件，我会一直支持下去的！


### 版本v1.0
API导出连着的图片时，会出现很多`<br />`，这时连续图片中只有第一张图片会被识别
```
![image.png](https://cdn.nlark.com/xxx1.png) />![image.png](https://cdn.nlark.com/xxx2.png) />![image.png](https://cdn.nlark.com/xxx3.png)

```
为了解决这一问题，在原来的ExportMD基础上，我增加了正则表达式，现在连续图片的导出已经没有问题
这里特别感谢ExportMD！
### 版本v1.1
实际使用的时候有遇到一些小问题，主要是接口限制等会导致有时候请求失败
这里使用[@stone0090](https://github.com/stone0090/ExportMD-rectify-pics)的[解决方案](https://github.com/stone0090/ExportMD-rectify-pics/blob/bf2b79ef0afaffcad78253cafa1760f45359623e/ExportMD.py#L198 )


修改为同步导出，且每次导出等待100ms
本人技术水平有限，感谢[@stone0090](https://github.com/stone0090/ExportMD-rectify-pics)!的修复


## 2、安装
### 环境要求
 - python >= 3.6

### 安装 python 依赖
```bash
pip install -r requirements.txt
```
---

## 3、使用

## 获取 namespace
知识库 namespace：知识库 URL 中路径部分

知识库 [https://www.yuque.com/YourYuqueUserName](https://www.yuque.com/YourYuqueUserName)  对应的 *namespace* 为 *YourYuqueUserName*

## 获取 token
请注意，目前只有超级会员才能开启token


## 使用 python3 运行
```bash
python ExportMD.py
```
## 输入namespace和token
`⬆ ⬇`移动，`space`选择，`a`全选，`Enter`确认
![image](https://user-images.githubusercontent.com/61380549/162611337-9b2f875f-6cf0-47d6-87ba-6aa6a7f5efef.png)

