# CanvasKeyFrames - HTML5 Canvas 图片序列帧播放工具[![npm][npm-image]][npm-url] [![Build Status][travis-image]][travis-url] 

[English Version](./readeMe_EN.md)

# CanvasKeyFrames

图片序列帧播放工具,用canvas操作图片动画，封装了常用方法。


* el      [canvas容器,必须是DOM对象]
	 * type    [图片模式，'array'和 'sprite'模式，array是图片对象数组，sprite是基于宽度扩展的单张雪碧图]
	 * imgs    [图片帧对象数组或单图，对应不同模式]
	 * options {\
				cover: 10, //指定封面帧，默认是0 \
			    fps: 30, //默认是24\
			    loop: 10 //初始化默认的循环次数，可以手动设置大于等于1的整数。在formTo中可以设置。默认是infinite。\
			    width: 300, //注意，隐藏元素是拿不到宽度的，所以特殊情况下需要指定宽度\
			    height: 300,\
          _iw: 300, // 雪碧图中单个图片的宽度\
          _ih: 300, // 雪碧图中单个图片的高度\
          framesCount: 10 // 雪碧图帧数\
               	}

## API

### CanvasKeyFrames(el, type, imgs, options)

- `el` canvas容器,必须是DOM对象
- `type` 图片模式，'array'和 'sprite'模式，array是图片对象数组，sprite是基于宽度扩展的单张雪碧图
- `imgs` 图片帧对象数组或单图，对应不同模式
- `options`
  - `cover` 指定封面帧，默认是0
  - `fps` 默认是24
  - `loop` 初始化默认的循环次数，可以手动设置大于等于1的整数。在formTo中可以设置。默认是infinite。
  - `width` 隐藏元素是拿不到宽度的，所以特殊情况下需要指定宽度
  - `height` 隐藏元素是拿不到宽度的，所以特殊情况下需要指定宽度
  - `_iw` 雪碧图中单个图片的宽度
  - `_ih` 雪碧图中单个图片的高度
  - `framesCount` 雪碧图帧数


### Install

* base

your html

```html
<script src="canvas-keyframes.js"></script>

```

* npm

```bash
npm i canvaskeyframes
```

your app.js

```javascript

import CanvasKeyFrames from 'canvaskeyframes'

```


### 方法介绍 

##### goto(n) 跳转到某一帧
##### next()  下一帧
##### prev()  上一帧
##### fromTo(from, to, loop, callback) 
`
 from     [启始帧（从0开始）]
  to       [结束帧数]
  loop     [循环次数，默认是infiniten]
  callback [回调函数]
  `
##### toFrom(to, from, loop, callback)
`
to       [启始帧（从高位开始）]
 from     [结束帧数（从低位结束）]
 loop     [循环次数，默认是infiniten]
 callback [回调函数]
 `
##### repeatplay(from, to, loop, callback)
`
fromto正着播一遍,然后回调fromBack,倒着播一遍，然后再回调toBack,进行逻辑判断
from     [启始帧（从0开始）]
to       [结束帧数]
loop     [循环次数，默认是infinite正播过去，再倒播回来]
callback [回调函数]
`
##### from(from, loop, callback)
`
 from     [启始帧（从0开始）]
 loop     [循环次数，默认是infinite]
 callback [回调函数]
`
##### to(to, loop, callback)
`
to       [结束帧数]
loop     [循环次数，默认是infinite]
callback [回调函数]
`
##### pause() 暂停动画
##### stop() 停止并回到第一帧或cover帧
##### play() 从当前位置播放动画，会继承上次使用fromTo、form或to的属性
##### destroy() 销毁对象

## 前端学习交流群，QQ群 : 692337464
## ![](https://github.com/wenyiweb/vuejs-fujun/blob/master/static/imgs/qq.png)

## 觉得有用，请我喝杯咖啡吧~
## ![](/static/wx.jpg)

## License

[MIT License](http://en.wikipedia.org/wiki/MIT_License)



[travis-image]: https://api.travis-ci.org/wenyiweb/canvasKeyFrames.svg?branch=master
[travis-url]: https://travis-ci.org/wenyiweb/canvasKeyFrames

[npm-image]: https://img.shields.io/npm/v/canvaskeyframes.svg?style=flat-square
[npm-url]: https://www.npmjs.com/package/canvaskeyframes
