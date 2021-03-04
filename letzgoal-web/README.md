# Letzgoal(01 齐跑响应式网站)

官网： https://www.letzgoal.com

<p>
   <h1><a href="https://fish-1256004880.cos.ap-shenzhen-fsi.myqcloud.com/index.html#letzgoal">视频demo</a></h1>
</p>

- [All](#all)
- [Login](#login)
- [Homepage](#homepage)
- [Challenge](#challenge)
- [Achievement](#achievement)
- [Team](#team)
- [Q&A](#q-a)
- [TNC](#tnc)
- [AboutUs](#about-us)
- [WebviewTickets](#webview-tickets)
- [WebviewInfo](#webview-info)
- [遇到的问题](#遇到的问题)

## all

- 整站添加 apple-app-site-association.json、assetlinks.json 使得能通过 universal link 以及 deeplink 跳转到 app
- 使用 helmet-csp 设置 Content-Security-Policy 头部
- 封装了一个 npm module，用于整站设置`<img>` 的 srcset 跟 size，使得根据不同屏幕展示不同质量的图片(比如 375 的屏幕使用 720p 的图片，1024 屏幕使用 1080p 的图片)，从而提升性能
- 使用节流函数来处理 resize 事件
- 页头页脚：头部固定，底部位置随着正文的高度而变化，如果屏幕高度容得下正文+footer，则 footer 固定在页面底部，否则 footer 滚动。具体实现：

```
#css
main {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
}
.container {
  flex: 1;
}
#html
<main>
  <div class="container">
  </div>
  <footer></footer>
</main>
```

## login

- 开发 `01app-sso-for-webview`提供给 native app 登录，refreshtoken, 登出等功能。
<p align="center">
  <img src="https://fish-1256004880.cos.ap-shenzhen-fsi.myqcloud.com/images/letzgoal/%E7%99%BB%E5%BD%951.PNG" />
  <br />
  <img src="https://fish-1256004880.cos.ap-shenzhen-fsi.myqcloud.com/images/letzgoal/%E7%99%BB%E5%BD%952.PNG" />
</p>

## homepage

- 使用 css 媒体查询进行响应式设计
- 电梯导航，通过点击 PC 端右边的按钮，可以跳转到对应的页面
- 使用 branchIO 生成的 URL 配合 qrcode.react 绘制分享二维码，通过点击移动端的按钮或者扫码 PC 端的二维码实现以下功能：
点击或者扫码二维码跳转到 branchIO url，如果已经安装过 app，则进入 app 对应的页面，否则进入 appStore 或者 google play，如果 appStore 或者 google play 没有安装，则跳转到 branchIO 控制台预先设置好的 url
<p align="center">
  <img src="https://fish-1256004880.cos.ap-shenzhen-fsi.myqcloud.com/images/letzgoal/homepage_pc.png" />
  <br />
  <img src="./images/首页.png"" />
</p>

## challenge

- 使用 react-truncate 实现文字的折叠与展开功能，本身 react-truncate 不支持中文，最终使用 patch-package 修改支持中文，右边的二维码跟首页的功能一样，都是通过 branchIO 跳转。
- 根据不同的 userAgent（比如 WhatsApp、facebookexternalhit、Twitterbot）, 展示不同的 Metatags
<p align="center">
  <img src="https://fish-1256004880.cos.ap-shenzhen-fsi.myqcloud.com/images/letzgoal/%E5%88%86%E4%BA%AB%E6%8C%91%E6%88%98.png" />
</p>

## achievement

如 challenge 页面

<p align="center">
  <img src="https://fish-1256004880.cos.ap-shenzhen-fsi.myqcloud.com/images/letzgoal/%E5%88%86%E4%BA%AB%E5%A5%96%E7%AB%A0.png" />
</p>

## team

如 challenge 页面

<p align="center">
  <img src="https://fish-1256004880.cos.ap-shenzhen-fsi.myqcloud.com/images/letzgoal/%E5%88%86%E4%BA%AB%E5%9B%A2%E9%98%9F.png" />
</p>

## q-a

<p align="center">
  <img src="https://fish-1256004880.cos.ap-shenzhen-fsi.myqcloud.com/images/letzgoal/%E5%B8%B8%E8%A7%81%E9%97%AE%E9%A2%98_00.png" />
</p>

## tnc

<p align="center">
  <img src="https://fish-1256004880.cos.ap-shenzhen-fsi.myqcloud.com/images/letzgoal/%E9%9A%90%E7%A7%81%E6%9D%A1%E6%AC%BE_00.png" />
</p>

## about-us

<p align="center">
  <img src="https://fish-1256004880.cos.ap-shenzhen-fsi.myqcloud.com/images/letzgoal/%E5%85%B3%E4%BA%8E%E6%88%91%E4%BB%AC_00.png" />
</p>

# event-web

<p align="center">
   <h1><a href="https://fish-1256004880.cos.ap-shenzhen-fsi.myqcloud.com/index.html#eventWeb">视频demo</a></h1>
</p>

## webview-tickets

- 使用 sso 单点登录，material-ui 编写页面 UI 组件，redux-form 处理表单数据，支持 darkmode 模式，跟随 app 的主题模式

- 通过 window.ReactNativeWebView.postMessage([messageBody]) 向 app 发送数据与 app 进行交互。
<p align="center">
  <img src="https://fish-1256004880.cos.ap-shenzhen-fsi.myqcloud.com/images/letzgoal/eventWeb-%E9%80%89%E6%8B%A9ticket.PNG" />
  <br/>
  <img src="https://fish-1256004880.cos.ap-shenzhen-fsi.myqcloud.com/images/letzgoal/eventWeb-%E9%80%89%E6%8B%A9ticket-darkmode.PNG" />
</p>

## webview-info

技术点同 webview-tickets

<p align="center">
  <img src="https://fish-1256004880.cos.ap-shenzhen-fsi.myqcloud.com/images/letzgoal/eventWeb-%E5%A1%AB%E5%86%99%E8%B5%84%E6%96%99.PNG" />
  <br/>
  <img src="https://fish-1256004880.cos.ap-shenzhen-fsi.myqcloud.com/images/letzgoal/eventWeb-%E5%A1%AB%E5%86%99%E8%B5%84%E6%96%99-darkmode.PNG" />
</p>

## 遇到的问题

1. 开发跟随 app 的主题颜色的时候遇到了一个问题，刚开始写了个 usePrefersColorScheme 的 hook 来实现 darkmode 跟 lightMode 的切换，由于这个 hook 使用了 window.matchMedia('(prefers-color-scheme: dark)')，只能在 client 端才能判断，这样就有可能会出现闪屏，比如我们默认是 darkmode, app 使用的是 lightmode，在 client 渲染的时候默认先是 darkmode 的背景，之后才变成 lightmode，这样体验不好。后面使用了 cookie，app 将使用的 themeMode 放入到 cookie，再通过 express 在 server 那边读取 cookie，在经过 ssr 返回 html 之后，就会跟 app 的 themeMode 同步了，不在出现闪屏现象

2. 通过 window.ReactNativeWebView.postMessage([messageBody])跟 app 交互的时候，ios 需要按照 window.webkit.messageHandlers[name].postMessage([messageBody])来传递消息，参考这里 https://developer.apple.com/documentation/webkit/wkusercontentcontroller/1537172-add, 然后去看了一下 react-native-webview 的源码，发现 react-native 采用注入 js 的方法使得 ios 也兼容这种写法 window.ReactNativeWebView.postMessage(<messageBody>)， 参看 https://github.com/react-native-webview/react-native-webview/blob/22a60fd23a9ce396b11f498a6b338bf16510981b/apple/RNCWebView.m#L1220-L1238

3. cypress 使用 nock.js mock 数据的时候，在 local 执行 cypress run 测试的时候没有问题，在 travis 上跑发现出了问题，发现部分 test case 无法 mock 数据，然后去查看官方文档，issues，google 都没找到结果，然后改了下配置，在 docker 模拟了 travis 的环境进行测试，发现了同样的问题。去看 error-log 发现 docker 里面的 web 服务启动了多进程，在进入 docker container 查看，发现 devops 在 pm2.config.js 使用了 cluster 模式，并设置了 PM2_INSTANCES=max，导致了一个结果，比如在 nock.js mock 数据的时候被 process0 处理，cypress 执行 cy.visit 的时候被 process1 处理，这就导致了这个问题，部分页面在 visit 的时候拿不到 mock 的数据。最后的解决方法是通过 docker-comnpose 设置了一个 environment: PM2_INSTANCES=1。
