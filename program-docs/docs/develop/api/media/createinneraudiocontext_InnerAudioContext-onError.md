---
title: InnerAudioContext.onError
header: develop
nav: api
sidebar: createinneraudiocontext_InnerAudioContext-onError
---




**解释**：音频播放错误事件

 
 ## 方法参数
Function callback

## 示例

<a href="swanide://fragment/5fd261029e57512a9ca106f81328f5e91574546056156" title="在开发者工具中预览效果" target="_self">在开发者工具中预览效果</a>

### 扫码体验

<div class='scan-code-container'>
    <img src="https://b.bdstatic.com/miniapp/assets/images/doc_demo/fragment_InnerAudioContextOnError.png" class="demo-qrcode-image" />
    <font color=#777 12px>请使用百度APP扫码</font>
</div>

### 图片示例 


<div class="m-doc-custom-examples">
    <div class="m-doc-custom-examples-correct">
        <img src="https://b.bdstatic.com/miniapp/image/InnerAudioContextOnError.gif">
    </div>
    <div class="m-doc-custom-examples-correct">
        <img src=" ">
    </div>
    <div class="m-doc-custom-examples-correct">
        <img src=" ">
    </div>     
</div>

###  代码示例 



* 在 swan 文件中

```html
<view class="container">
    <view class="card-area">
        此页面遇到音频播放错误事件会弹窗提示
    </view>
</view>
```

* 在 js 文件中

```javascript
Page({
    onLoad() {
        const innerAudioContext = swan.createInnerAudioContext();
        innerAudioContext.src = 'https://vd3.bdstatic.com/mda-ic7mxzt5cvz6f4y5/mda-ic7mxzt5cvz6f4y5.mp3';
        innerAudioContext.autoplay = false;
        innerAudioContext.onPlay(res => {
            swan.showToast({
                title: 'onplay',
                icon: 'none'
            });
        });
        innerAudioContext.onError(err => {
            swan.showModal({
                title: 'onError',
                content: JSON.stringify(err)
            });
            console.log('onError', res);
        });
        innerAudioContext.play();
        this.innerAudioContext = innerAudioContext;
    }
});
```