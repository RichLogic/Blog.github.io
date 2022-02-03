---
layout: default
title: 如何搭建造专属自己的博客
nav_order: 2
---

# 如何搭建造专属自己的博客
{: .no_toc }

写作日期：2022-02-03
{: .fs-2 .text-grey-dk-000 }

阅读时间：15 min
{: .fs-2 .text-grey-dk-000 }

**目录**
{: .fs-6}

1. TOC
{:toc}

---

## 快速搭建个人主页
<br/>

本博客是用 **GitHub Pages** 搭建的博客，非常简单、易上手。

A. 首先，你要有一个 GitHub 账号

B. 为博客单独创建一个项目，项目名称格式如下: `${github.name}.github.io`

![Image.png]({% link image/first/github_project.png %})
    
    注意：项目名称一定要写对，不然 GitHub 不会为你创建个人主页。

C. 在项目中创建 `index.html`, 写入“Hello World”，恭喜你，你的个人主页已经搭建好了。

D. 官方教程如下: [GitHub Pages 官网](https://pages.github.com/)

---

## 使用自定义主题
<br/>

**GitHub Pages** 如果只能显示 HTML 文件，那写博客也太麻烦了。**GitHub Pages** 为我们提供了 `Jekyll` 用于自定义主题。

众所周知，GitHub 与 Ruby 关系密切，所以不出意外的，`Jekyll` 也是一个 Ruby 软件。`Jekyll` 可以让我们用 Markdown 写作并自由更换主题。具体教程按照如下链接：[Jekyll 安装教程](https://jekyllrb.com/docs/)

![Image.png]({% link image/first/jekyll.png %})

    注意：一定要按照说明安装好 `Ruby` 和 `Gem` ！！（也就是截图上的步骤 1）

- 安装好 Jekyll 后，可以在[Jekyll 开源主题](https://github.com/topics/jekyll-theme) 挑选一个喜欢的主题，按照当中的教程选择安装。

- **Tips：**在本地运行 `bundle exec jekyll serve` , 并访问 4000 端口就可以进行本地预览了，方便调试。

---

## 使用自己的域名
<br />

经过上面两个步骤，你已经拥有了一个精美的个人主页了。但是，还有没有什么更 Geek 的事情可以做呢？那当然是使用自己的域名了！

### 购买域名

阿里云已经收购了万网，可以通过 [阿里云](https://wanwang.aliyun.com/domain/) 购买喜欢的域名。

但是阿里云的价格有些偏高，在此给大家推荐 [NameSilo](https://www.namesilo.com/)，相同的域名，这个网站会比阿里云便宜一些。

### GitHub 设置

A. 进入 GitHub 账户设置，点击 Pages，点击右侧 `Add a domain`，输入域名，会显示出两个 **TXT** 记录，准备复制。

![Image.png]({% link image/first/github_account_setting.png %})

B. 进入 `${github.name}.github.io` 项目设置，点击 Pages，在 Custom domain 添加域名

![Image.png]({% link image/first/github_project_setting.png %})

### DNS 设置

A. 我们用 **Cloudflare** 做域名注册，首先需要注册一个 [**Cloudflare**](https://www.cloudflare.com/zh-cn/) 账号。

B. 添加站点，输入自己的域名，然后点击左侧的 **DNS**，跳转到 DNS 设置

![Image.png]({% link image/first/cloud_dns.png %})

a. 设置 **TXT** 记录，把 **GitHub** 中的粘贴过来即可

b. 设置 **CNAME** 记录，`@` 和 www 都指向 GitHub 配置为你分配的域名，并设置为已代理

    1. `@` 是对应第一行的 CNAME 记录，也就是对应不加任何前缀的情况
    2. 设置为已代理，Cloudflare 会做缓存，减少网站的压力

c. 将两个 NS 值，复制回 NameSilo，如下图

![Image.png]({% link image/first/namesilo.png %})

### 安全性设置

A. 点击左侧 **SSL/TLS概述**，右侧选择**灵活**，如下图。这样浏览器在访问我们主页的时候，会强制使用 HTTPS

![Image.png]({% link image/first/cloud_TLS.png %})

B. 点击 **SSL/TLS边缘证书**，右侧选择 **始终使用 HTTPS**， 将最低 TLS 版本设置成 **TLS 1.3**

---

## 总结
<br/>

本片博文是我的第一篇博客，也是根据自己搭建这个博客的经历写了这篇文章。

搭建博客主要是一个学习与玩的过程，这篇也只是浅尝辄止，抛砖引玉，希望给想要自己搭建博客的同学一些帮助。

