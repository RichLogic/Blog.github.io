---
layout: default
title: 如何搭建造专属自己的博客
nav_order: 1
---

# 如何搭建造专属自己的博客
{: .no_toc }

1. TOC
{:toc}

---

## 快速搭建个人主页
<br/>

本博客是用 **GitHub Pages** 搭建的博客，非常简单、易上手。

A. 首先，你要有一个 GitHub 账号

B. 为博客单独创建一个项目，项目名称格式如下: `${github.name}.github.io`

![Image.png](https://res.craft.do/user/full/59f30c7a-efda-901e-ba05-a83d5939de7a/doc/9BF509D4-B290-4CD5-A029-D0E74532BD8A/637C0B14-063D-497E-8583-043520DB50F3_2/guhQsIT5iGDapy4WZCmRThIOQA15HTHfCQ3Zly8h3A0z/Image.png)
    
    注意：项目名称一定要写对，不然 GitHub 不会为你创建个人主页。

C. 在项目中创建 `index.html`, 写入“Hello World”，恭喜你，你的个人主页已经搭建好了。

D. **官方教程如下:** [GitHub Pages 官网](https://pages.github.com/)

---

## 使用自定义主题
<br/>

**GitHub Pages** 如果只能显示 HTML 文件，那写博客也太麻烦了。**GitHub Pages** 为我们提供了 `Jekyll` 用于自定义主题。

众所周知，GitHub 与 Ruby 关系密切，所以不出意外的，`Jekyll` 也是一个 Ruby 软件。`Jekyll` 可以让我们用 Markdown 写作并自由更换主题。[Jekyll 安装教程](https://jekyllrb.com/docs/)

![Image.png](https://res.craft.do/user/full/59f30c7a-efda-901e-ba05-a83d5939de7a/doc/9BF509D4-B290-4CD5-A029-D0E74532BD8A/40D3E228-51DB-470F-89A8-677DE6504167_2/LyUs5FaPQxpugTCF0InR5g1VSvDkwL3ENoS3YzdOWK4z/Image.png)

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

![Image.png](https://res.craft.do/user/full/59f30c7a-efda-901e-ba05-a83d5939de7a/doc/9BF509D4-B290-4CD5-A029-D0E74532BD8A/DE470063-8378-4D10-868B-35C111303165_2/IvBbTNgbN6rAoPH6FXJYUk1AS62y3rGg7kCBQz7gVLgz/Image.png)

B. 进入 `${github.name}.github.io` 项目设置，点击 Pages，在 Custom domain 添加域名

![Image.png](https://res.craft.do/user/full/59f30c7a-efda-901e-ba05-a83d5939de7a/doc/9BF509D4-B290-4CD5-A029-D0E74532BD8A/4AA9CAE0-2CDC-4810-8514-A8CCFD2B0B25_2/equxcs5B0nVjul2ubhTpiKs9v8eGtlCyJozyFD4Bou0z/Image.png)

### DNS 设置

A. 我们用 **Cloudflare** 做域名注册，首先需要注册一个 [**Cloudflare**](https://www.cloudflare.com/zh-cn/) 账号。
B. 添加站点，输入自己的域名，然后点击左侧的 **DNS**，跳转到 DNS 设置

![Image.png](https://res.craft.do/user/full/59f30c7a-efda-901e-ba05-a83d5939de7a/doc/9BF509D4-B290-4CD5-A029-D0E74532BD8A/FD317963-4B8B-4714-A729-6BF7AA264B11_2/6MP4Za7mS124hTSBXqLxNmeJGpzJ86vShLcGd2VcIYkz/Image.png)

a. 设置 **TXT** 记录，把 **GitHub** 中的粘贴过来即可

b. 设置 **CNAME** 记录，`@` 和 www 都指向 GitHub 配置为你分配的域名，并设置为已代理

    1. `@` 是对应第一行的 CNAME 记录，也就是对应不加任何前缀的情况
    2. 设置为已代理，Cloudflare 会做缓存，减少网站的压力

c. 将两个 NS 值，复制回 NameSilo，如下图

![Image.png](https://res.craft.do/user/full/59f30c7a-efda-901e-ba05-a83d5939de7a/doc/9BF509D4-B290-4CD5-A029-D0E74532BD8A/E316453C-B57A-4220-BB07-D2CB8B36F736_2/yF9NXeenj34BoueKalPRyI0HyaTyK64CwQET7gvWu4gz/Image.png)

### 安全性设置

A. 点击左侧 **SSL/TLS概述**，右侧选择**灵活**，如下图。这样浏览器在访问我们主页的时候，会强制使用 HTTPS

![Image.png](https://res.craft.do/user/full/59f30c7a-efda-901e-ba05-a83d5939de7a/doc/9BF509D4-B290-4CD5-A029-D0E74532BD8A/EC5E735A-8753-4794-A341-40A024CA1357_2/KGIkUSthGmcrFyE7r63mSEDyd9vg07iZMVZxae1xOF8z/Image.png)

B. 点击 **SSL/TLS边缘证书**，右侧选择 **始终使用 HTTPS**， 将最低 TLS 版本设置成 **TLS 1.3**

---

## 总结
<br/>

本片博文是我的第一篇博客，也是根据自己搭建这个博客的经历写了这篇文章。

搭建博客主要是一个学习与玩的过程，这篇也只是浅尝辄止，抛砖引玉，希望给想要自己搭建博客的同学一些帮助。

