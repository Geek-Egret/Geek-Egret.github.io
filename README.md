# [极鹭 | Geek-Egret](https://geek-egret.github.io/)
## 文章编写
```markdown
---
layout:     post
title:      名称
subtitle:   子标题
date:       日期
author:     作者
header-img: 头图
preview-img: 预览图
catalog: 	 true
tags:   标签
---

....(context)
```
编写完成后必须命名为 `xxxx-xx-xx-title`（日期-标题）的结构，并放置于 <b>`_posts`</b> 文件夹内
## <b>Github Pages</b> 建站流程
### 域名
- 购买域名
    - 国内外域名区别
        - 国内域名商购买域名需要备案 <b>时间久</b>

        - 国外域名商购买域名无需备案 <b>支付方式有限</b>
    - 推荐购买方式
        | 域名商 | 国家/地区 | 说明 |
        | :----: | :------: | ---- |
        | <b>GoDaddy | 美国 | 可以使用支付宝，价格较贵，该域名商为本网站域名服务商 | 
        | <b>NameSilo | 美国 | 似乎无法使用支付宝，但是可以使用银联，价格实惠 |
        - 由于国内域名商提供备案条件需要租用云服务器达到规定时间，且国内域名无法指向`github.io`，性价比低 <b>不推荐</b>
- 域名DNS解析
    - 需在域名商处完成DNS解析操作，以本网站域名服务商 <b>GoDaddy</b> 为例进行演示

    ![image_godaddy_0](/img/2025-2-3-网站成功建站啦/Snipaste_2025-02-03_14-55-07.png)

    - 打开图示界面，选择新增记录，填写以下5个记录
    
        | 类型 | 名称 | 内容值 | TTL |
        | :-: | :--: | :----: | :-: |
        | A | @ | 185.199.108.153 | 1小时 |
        | A | @ | 185.199.109.153 | 1小时 |
        | A | @ | 185.199.110.153 | 1小时 |
        | A | @ | 185.199.111.153 | 1小时 |
        | CNAME | www | <b>e.g.</b>{username}.github.io | 1小时 |
- <b>Github Pages</b> 申请
    - 新建个人 <b>公开Public</b> 仓库，仓库名称为 `{username}.github.io` 

    - 打开 <b>Setting</b>，选择左边栏的 `Pages` 选项

    - 将 `/(root)` 更改为 `/docs` 后再改回 `/(root)` 以此来使能Github Pages，如下图

    ![image_github_0](/img/2025-2-3-网站成功建站啦/Snipaste_2025-02-03_15-10-31.png)

    - 填入刚刚所购买的域名到下方 <b>Custom domain</b> 处，可先退出，等待DNS传播后勾选 <b>Enforces HTTPS</b>，如下图

    ![image_github_1](/img/2025-2-3-网站成功建站啦/Snipaste_2025-02-03_15-14-22.png)

    - 上述流程结束后，将可以使用购买的域名进行网页访问

### 静态网页工程简介
> 本网页使用 <b>JEKYLL</b> 进行网页静态搭建，参考了[<b>qiubaiying.github.io</b>](https://github.com/qiubaiying/qiubaiying.github.io/tree/master) 项目
- 从 [<b>Geek-Egret.github.io</b>](https://github.com/Geek-Egret/Geek-Egret.github.io) 处 <b>clone</b> 仓库至本地
- 仓库结构

    ```shell
    ├─css           CSS样式
    ├─fonts         字体
    ├─img           Page图片
    ├─js            前端
    ├─less          CSS拓展
    ├─pwa           网页标签ICO
    │  └─icons
    ├─_includes     
    ├─_layouts      布局
    └─_posts        文章
    ```
- 以下列出需要修改的 <b>文件</b> 的说明

    | 文件 | 说明 |
    | :-: | -------- |
    | [_config.yml](../_config.yml) | 网页配置文件 |
    | [index.html](../index.html) | 主页 HTML 文件 |
    | [about.html](../about.html) | 关于页面 HTML 文件 |
    | [tags.html](../tags.html) | 标签页面 HTML 文件 |

- 以下列出需要修改的 <b>图像文件夹/文件</b> 说明

    | 文件夹 | 说明 |
    | :-: | -------- |
    | [pwa/icons](../pwa/icons/) | 网页应用图标（如手机端将网页添加到桌面时的图标） |
    | [img](../img) | 网页图标 |

    - <b>img/ </b>文件说明

    | 文件 | 说明 |
    | :---: | ---- |
    | avatar.jpg | 用户头像 |
    | favicon.ico | 网页标签图标 |
    | apple-touch-icon.png | <b>Apple</b> 网页标签图标 |
    | 404-bg.jpg | <b>404</b> 图 |
    | home-header.jpg | 主页 <b>HOME</b> 头图 |
    | about-header.jpg | 关于 <b>ABOUT</b> 页面头图 |
    | tag-header.jpg | 标签 <b>TAGS</b> 页面头图 |

### 静态网页工程修改
- 对于除 `_config.yml` 外的文件的修改，主要更改文件开头的内容
    ```
    ---
    title:          标题
    layout:         布局
    description:    简介
    header-img:     头图
    ---
    ```
- 对于 `_config.yml` 文件，有以下几处需要修改

    | 修改位置 | 说明 |
    | :-----: | ---- | 
    | # Site settings | 网站设置 |
    | # Sidebar settings | 边栏设置 |
    | # SNS settings | 链接网站设置 |
    | # Friends | 友站链接设置 |

❗❗❗目前，本工程只支持以下几个网站的链接

|     |     |     |     |
| :-: | :-: | :-: | :-: |
| BiliBili | 简书 | 知乎 | Github |

若要添加新的网站链接，请自行去 [<b>_include/footer.html</b>](../_includes/footer.html)和[<b>_layouts/page.html</b>](../_layouts/page.html) 并参照其他网页的添加方式自行添加😁
