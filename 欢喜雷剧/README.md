# 欢喜雷剧 APP

- 支持后台播放音乐
- 支持视频播放
  ios 同步开发，暂时没有上线

<p>
   <h1><a href="https://fish-1256004880.cos.ap-shenzhen-fsi.myqcloud.com/index.html#huanxileiju">视频demo</a></h1>
</p>

- [SplashScreen](#splash-screen)
- [Homepage](#homepage)
- [MusicList](#music-list)
- [MusicPlayer](#music-player)
- [VideoList](#video-list)
- [VideoPlayer](#video-player)
- [Mine](#mine)

## splash-screen

- 使用 react-native-splash-screen 做启动页

<p align="center">
  <img src="https://fish-1256004880.cos.ap-shenzhen-fsi.myqcloud.com/images/huanxi/%E5%90%AF%E5%8A%A8%E9%A1%B5.png" />
</p>

## homepage

- 使用 react-content-loader 实现数据加载时的骨架屏
- 使用 tcb-js-sdk 调用腾讯云函数获取数据
- 使用 react-hooks-global-state 管理全局数据
- 支持下拉刷新
<p align="center">
  <img src="https://fish-1256004880.cos.ap-shenzhen-fsi.myqcloud.com/images/huanxi/hx-%E9%A6%96%E9%A1%B5.JPG" />
</p>

## music-list

- 使用 flex 分栏布局
- 数据懒加载，虚拟列表，下拉刷新

<p align="center">
  <img src="https://fish-1256004880.cos.ap-shenzhen-fsi.myqcloud.com/images/huanxi/hx-%E9%9F%B3%E4%B9%90%E5%88%97%E8%A1%A8.JPG" />
</p>

## music-player

- 使用 react-native-video 实现音乐播放功能
- 支持封面动画跟随音乐播放，并支持后台音乐播放，离开播放页面之后以浮窗的形式显示正在播放的音乐，点击浮窗可回到播放页面，长按浮窗则关闭音乐
- 支持点击快进，拖动快进
- 调用原生 api 进行分享
<p align="center">
  <img src="https://fish-1256004880.cos.ap-shenzhen-fsi.myqcloud.com/images/huanxi/hx-%E9%9F%B3%E4%B9%90%E6%92%AD%E6%94%BE.JPG" />
  <br />
  <img src="https://fish-1256004880.cos.ap-shenzhen-fsi.myqcloud.com/images/huanxi/%E5%88%86%E4%BA%AB%E9%A1%B5%E9%9D%A2.png" />
</p>

## video-list

<p align="center">
  <img src="https://fish-1256004880.cos.ap-shenzhen-fsi.myqcloud.com/images/huanxi/hx-%E8%A7%86%E9%A2%91%E5%88%97%E8%A1%A8.JPG" />
</p>

## video-player

- 使用 react-native-video 实现音乐播放功能
- wifi 状态下自动播放视频
- 支持点击快进，拖动快进
- 全屏状态下修改返回键的默认返回行为，改成退出全屏
- 使用 react-native-orientation-locker 配合 react-native 的 Dimensions、StatusBar 等实现全屏非全屏效果

<p align="center">
  <img src="https://fish-1256004880.cos.ap-shenzhen-fsi.myqcloud.com/images/huanxi/hx-%E8%A7%86%E9%A2%91%E6%92%AD%E6%94%BE.JPG" />
</p>

## mine

- 使用 react-native-qrcode-svg 生成分享 app 的二维码
- 支持检测更新 app：调用 api 对比当前 appVersion，使用 react-native-fs 下载安装包，下载完调用 react-native-apk-installer-n 来进行安装 app
<p align="center">
<img src="https://fish-1256004880.cos.ap-shenzhen-fsi.myqcloud.com/images/huanxi/%E6%88%91%E7%9A%84.png">
</p>
