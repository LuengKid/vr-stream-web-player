# VR Stream Web Player (VR直播网页播放器)

##项目介绍

利用VR场景作为背景,接入直播视频流,进行在VR场景内观看直播的网页播放器.

##项目演示

[VR直播网页播放demo][demo] (可在PC/Android/iphone 利用chrome浏览器打开)

## 项目相关

本项目基于VR场景构造github项目 [WebVR Boilerplate][wb].

用 three.js 对VR场景进行构造,利用 [facebook transform][fbtf] 将全景视频转换为 cubemap 视频再进行展示.

利用 [hls.js][hls] 进行H5内播放直播视频.



## 直播源

本项目现利用 [panda.tv][pd] 获取直播源.调用了部分 [panda.tv][pd] 接口.如有侵权,请联系作者.

因为JS跨域问题,现利用nginx进行反向代理用于访问对应接口及直播源.

部分直播可能有问题.



## 适配平台

本项目可以适配手机,可以在Android/iphone手机的chrome浏览器上进行播放.

在PC端chrome可以流畅播放直播及背景视频. 

## nginx反向代理配置

    resolver 114.114.114.114;
    location ~* ^/u/(.*)$ {
        proxy_pass http://$1?$args;
    }
       

### 联系作者:Kid Lueng

 QQ交流群: 241587879(验证信息:VR直播) e-mail:100520140@qq.com

## 相关项目

- [WebVR Boilerplate][wb]: https://github.com/borismus/webvr-boilerplate
- [facebook transform][fbtf]: https://github.com/facebook/transform
- [hls]: https://github.com/dailymotion/hls.js
- [three.js]: https://threejs.org


[wb]: https://github.com/borismus/webvr-boilerplate
[fbtf]: https://github.com/facebook/transform
[hls]: https://github.com/dailymotion/hls.js
[three.js]: https://threejs.org
[pd]: http://panda.tv
[demo]:http://vr.kidlueng.com