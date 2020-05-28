---
title: 记搭建Blog中遇到的那些事儿
date: 2020-05-28 19:06:01
tags: [Hexo, Fluid]
index_img: https://raw.githubusercontent.com/Hadymic/PersonalPicBed/master/img/Snipaste_2020-05-28_21-53-39.png
---

# ~~从0开始建站~~

本博客采用了`Hexo + Github Pages`的方案（主要是不花钱）。关于`Hexo`的主题，在`GitHub`中经过多番挑选，最终选用了`Fluid`。网上教程那么多，这里就不详述了，主要想记录一下搭建过程中遇到的问题。

# Git与SSH

网上很多教程都配置了以`SSH`的方式连接`Github`仓库，但在`_config.yml`中却依旧使用`HTTPS`的方式进行连接。这就导致了配置完成后即便以`SSH`连接`Github`成功，出现以下代码即为成功。

```shell
$ ssh -T git@github.com
Hi Hadymic! You've successfully authenticated, but GitHub does not provide shell access.
```

在部署到`Github`上时依旧提示账号登录，所以在`_config.yml`中需要使用`SSH`的方式进行连接。

```yml
deploy:
  type: git
  repo: 
    github: git@github.com:Hadymic/hadymic.github.io.git
  branch: master
```

# Fluid主题修改

## 首页Slogan改为一言

![首页一言展示](https://raw.githubusercontent.com/Hadymic/PersonalPicBed/master/img/%E9%A6%96%E9%A1%B5%E4%B8%80%E8%A8%80%E5%B1%95%E7%A4%BA.gif)

主要有两个想法，首页Slogan改为一言，同时保留打字机的效果。

由于个人前端水平有限，只能用些暴力的方法实现（能用就行）。

需要修改的文件有两个，目录如下

```
typed.ejs : /themes/fluid/layout/_partial/plugins/typed.ejs
fluid_config.yml : /source/_data/fluid_config.yml
```

在`fluid_config.yml`的`index`下增加一行

```yml
index:
  ...
  slogan:  # 首页副标题的独立设置
    enable: true  # 为 false 则不显示任何内容
    hitokoto: true # 为 true 则启用一言
    text:  # 为空则按 hexo config.subtitle 显示
```

将`typed.ejs`如下更改

```ejs
<% if(theme.fun_features.typing.enable){ %>
  <%- js_ex(theme.static_prefix.typed, "/typed.min.js") %>
  <script>
    if (<%- theme.index.slogan.hitokoto %> && "<%- data.subtitle %>" == "") {
      fetch('https://v1.hitokoto.cn')
          .then(response => response.json())
          .then(data => {
            var typed = new Typed('#subtitle', {
              strings: [
                '  ',
                data.hitokoto + "&nbsp;",
              ],
              cursorChar: "<%- theme.fun_features.typing.cursorChar %>",
              typeSpeed: <%- theme.fun_features.typing.typeSpeed %>,
              loop: <%- theme.fun_features.typing.loop %>,
            });
          })
            .catch(console.error)
    } else {
      var typed = new Typed('#subtitle', {
        strings: [
          '  ',
          "<%- data.subtitle %>&nbsp;",
        ],
        cursorChar: "<%- theme.fun_features.typing.cursorChar %>",
        typeSpeed: <%- theme.fun_features.typing.typeSpeed %>,
        loop: <%- theme.fun_features.typing.loop %>,
      });
    }
    typed.stop();
    $(document).ready(function () {
      $(".typed-cursor").addClass("h2");
      typed.start();
    });
  </script>
<% } %>
```

效果在本博客首页也看到了。

如果还有其他需要，在本博客的`Github`项目下的`dev`分支保存了所有源代码。