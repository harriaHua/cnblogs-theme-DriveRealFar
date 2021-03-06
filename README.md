# DriveRealFar
一款博客园主题，给自己做的，有兴趣就拿去用吧

>[ Honey Take My Hand ](https://music.163.com/song?id=1312528250&userid=279721043)
>
>Pack our bags and get in that car
>
>收拾行李上那辆车
>
>Leave a little note and we'll drive real far
>
>留个小纸条，我们会开很远的
>
>Let's get out, we can leave this city
>
>我们出去吧，我们可以离开这个城市
>
>Let's drive to the open air
>
>我们开车到露天去吧
>
>Yeah the countryside is so pretty
>
>是的，乡村很漂亮
>
>With the wind blowing in your hair
>
>风吹过你的头发
>
>We can look back some day
>
>我们总有一天会回顾过去的
>
>Baby don't you understand?
>
>宝贝，难道你不明白吗?
>
>That we only get one life, I wanna make it count
>
>我们只有一次生命，我想让它有意义
>
>

## 特性

- 明暗两种模式
- 主题颜色可用浏览器默认色盘自定义
- 带背景音乐

## 模样

![image-20220111191800542](https://i.bmp.ovh/imgs/2022/01/bb62f7e2cceacebf.png)

## 前提说明

使用之前请确认已申请js权限

本主题基于博客园主题BlueSky进行的更改

为避免不必要冲突，请打开禁用模板默认CSS

## 页面定制CSS代码

后面的hljs都是代码高亮样式

```css
.post > .clear {
  position: fixed;
  top: 0;
  left: 0;
  width: 100vw;
  height: 100vh;
  background-color: rgb(240, 255, 255);
  opacity: 1;
  transition: opacity 1s;
}
.day .clear:last-of-type {
  width: 100vw;
  height: 100vh;
  position: fixed;
  background-color: rgb(240, 255, 255);
  top: 0;
  left: 0;
  opacity: 1;
  transition: opacity 1s;
}
pre table {
  overflow-x: screen;
}

#home #header #navigator {
  display: none;
}

.hljs {
  color: black;
  font-family: Consolas, Monaco, monospace !important;
}

.hljs-comment,
.hljs-quote {
  color: #717171;
}

.hljs-keyword,
.hljs-selector-tag,
.hljs-literal {
  color: #e96900;
}

.hljs-name {
  color: #2973b7;
}

.hljs-variable,
.hljs-template-variable {
  color: #660;
}

.hljs-string {
  color: #42b983;
}

.hljs-regexp,
.hljs-link {
  color: #080;
}

.hljs-title,
.hljs-tag,
.hljs-symbol,
.hljs-bullet,
.hljs-number,
.hljs-meta {
  color: #2973b7;
}

.hljs-section,
.hljs-class .hljs-title,
.hljs-type,
.hljs-attr,
.hljs-built_in,
.hljs-builtin-name,
.hljs-params {
  color: #2973b7;
}

.hljs-attribute,
.hljs-subst {
  color: #000;
}

.hljs-formula {
  background-color: #eee;
  font-style: italic;
}

.hljs-addition {
  background-color: #baeeba;
}

.hljs-deletion {
  background-color: #ffc8bd;
}

.hljs-selector-id,
.hljs-selector-class {
  color: #9b703f;
}

.hljs-doctag,
.hljs-strong {
  font-weight: bold;
}

.hljs-emphasis {
  font-style: italic;
}

span.cnb-code-toolbar-item {
  transition: all 0.4s ease;
}
span.cnb-code-toolbar-item:hover {
  color: rgb(66, 185, 131);
}

```

## 配置参数

### index.js文件顶部

``` js
let $config = {
  avatar: "https://s3.bmp.ovh/imgs/2022/01/c5f97d8b0b788deb.png",
  userLink: "https://www.cnblogs.com/harria/'",
  ico: "https://files.cnblogs.com/files/blogs/723350/xia.svg",
  bgm: {
    link: "https://music.163.com/song/media/outer/url?id=1312528250.mp3",
    autoPlay: 1,
    loop: 1,
    volume: 0.1, // 0~1
  },
  color: {
    defaultColor: "#202020",
    localStorage: 1,
  },
  mode: {
    defaultMode: "dark", // light | dark | auto
    localStorage: 1, // 0 | 1
    province: "上海",
  },
};
```

### 参数含义

#### avatar

- 类型：`String`
- 默认值：`null`

头像的地址

#### userLink

- 类型：`String`
- 默认值：`null`

用户主页的地址

#### ico

- 类型：`String`
- 默认值：`null`

标签页前面的图标地址

#### bgm

| 名称     | 类型     | 默认值/实例 | 描述                     |
| :------- | :------- | :---------- | :----------------------- |
| link     | `String` |             | 背景音乐直链             |
| autoPlay | `Number` |             | 是否在加载好之后自动播放 |
| loop     | `Number` |             | 是否循环播放             |
| volume   | `Number` |             | 音量大小                 |

#### color

| 名称         | 类型     | 默认值/实例 | 描述             |
| :----------- | :------- | :---------- | :--------------- |
| defaultColor | `String` |             | 默认主题颜色     |
| localStorage | `Number` |             | 是否使用本地存储 |

#### mode

| 名称         | 类型     | 默认值/实例 | 描述             |
| :----------- | :------- | :---------- | :--------------- |
| defaultMode  | `String` |             | 默认明暗模式     |
| localStorage | `Number` |             | 是否使用本地存储 |
| province     | `String` |             | 所使用省份       |

## 页脚HTML代码

```html
<div id="water"></div>

<script>
    let firstTime = new Date();
    document.addEventListener("DOMContentLoaded", (event) => {
    console.log(
        "加载时间",
        new Date().getTime() - firstTime.getTime(),
        "ms"
    );
    });
    window.addEventListener("load", (event) => {
    console.log(
        "渲染时间",
        new Date().getTime() - firstTime.getTime(),
        "ms"
    );
    });
    // 这里需要修改
    document.write(
      '<link href="https://blog-static.cnblogs.com/files/blogs/723350/computer_beta1.0.css" rel="stylesheet" type="text/css" media="screen" />'
    );
    if (
    navigator.userAgent.match(
        /(phone|pad|pod|iPhone|iPod|ios|iPad|Android|wOSBrowser|BrowserNG|WebOS)/i
    )
    ) {
        // 这里需要修改
    document.write(
        '<link href="https://blog-static.cnblogs.com/files/blogs/723350/phone_beta1.0.css" rel="stylesheet" type="text/css" media="screen" />'
    );
    console.log("phone");
    } else {
    console.log("computer");
    // document.write(
    //   '<link href="./less/index.css" rel="stylesheet" type="text/css" media="screen" />'
    // );
    }
</script>


<script src="https://cdn.staticfile.org/jquery/1.10.2/jquery.min.js"></script>
<script src="https://unpkg.com/color-js@1.0.3/color.js"></script>
<script src="https://cdn.jsdelivr.net/npm/ac-colors@1/dist/ac-colors.min.js"></script>
<script src="https://blog-static.cnblogs.com/files/blogs/723350/jquery.lineProgressbar.js"></script>
// 这里需要修改
<script type="text/javascript" src="https://blog-static.cnblogs.com/files/blogs/723350/index_beta1.0.js" ></script>

```

## 代码引入

下载仓库中 `index.js`  `computer.css` `phone.css` 

上传至博客园后台文件

同时修改页脚HTML代码中的地址，需要修改的地方已有`//这里需要修改`

提示

## 最后

疑问可以 `harria.hua@qq.com` 联系我
