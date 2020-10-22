# markrgba-css

## 1️⃣ 简介

Github：[https://github.com/SunSeekerX/markrgba-css](https://github.com/SunSeekerX/markrgba-css)

原作者：[https://gitee.com/CLQing/MarkrgbaCss_UniApp](https://gitee.com/CLQing/MarkrgbaCss_UniApp)



这是一些 css 的简写类名的库，用于开发 uni-app。适用于 vue+nvue 文件。

在写代码的过程中，写 css 是非常头疼的事情，例如：

1. **命名**；这应该是所有程序员的痛。
2. **写 dom 不能直接写 css**；html 和 css 通常不在一块，需要滑动很长才能找到 css 定义的地方。
3. **很多重复定义**；像 `diaplay: flex;`  这样的代码在 css 中写了太多太多

想写的标准规范。找了 bem 规范，实际用起来非常不方便。因为是结合 scss，如果我用了 & 那我我在文档中搜索 css 定义的地方非常不方便。

偶尔发现了类似 `fd-r pt-10 w-150 h-80 fw-w pr-15` 这样的写法。一开始看起来非常的乱，无法维护。

当我理解了之后真香！这就是经验的结晶。上面的意思是

```scss
.fd-r{flex-direction:row}
.pt-10 {padding-top: 10rpx;}
.w-150 {width:150rpx;}
.h-80 {height:80rpx;}
.fw-w{flex-wrap:wrap}
.pr-15 {padding-right: 15rpx;}
```

现在我的代码：

![hx.png](./assets/hx.png)





## 2️⃣ 快速上手

**安装**

```bash
npm i @limm/markrgba-css
# or yarn
yarn add @limm/markrgba-css
```



**在 uni-app vue 页面中使用**

`${app}/App.vue`

推荐全部引入，开启 `treeshaking` 会自动裁剪没有用到的类

```scss
/* #ifndef APP-NVUE */
@import '@limm/markrgba-css/index.css';
/* #endif */
```

按需引入

```scss
/* #ifndef APP-NVUE */
@import '@limm/markrgba-css/css/border.css';//只引入边框
@import '@limm/markrgba-css/css/color.css';//只引入颜色
@import '@limm/markrgba-css/css/font.css';//只引入文字
@import '@limm/markrgba-css/css/layout.css';//只引入布局
@import '@limm/markrgba-css/css/margin.css';//只引入外边距
@import '@limm/markrgba-css/css/other.css';//其他
@import '@limm/markrgba-css/css/padding.css';//只引入内边距
/* #endif */
```



**在 uni-app nvue 页面中使用**

`${app}/App.vue`

推荐全部引入，开启 `treeshaking` 会自动裁剪没有用到的类

```scss
/* #ifdef APP-NVUE */
@import '@limm/markrgba-css/nvue.css';
/* #endif */
```

按需引入

```scss
/* #ifndef APP-NVUE */
@import '@limm/markrgba-css/nvue/border.css';//只引入边框
@import '@limm/markrgba-css/nvue/color.css';//只引入颜色
@import '@limm/markrgba-css/nvue/font.css';//只引入文字
@import '@limm/markrgba-css/nvue/layout.css';//只引入布局
@import '@limm/markrgba-css/nvue/margin.css';//只引入外边距
@import '@limm/markrgba-css/nvue/other.css';//其他
@import '@limm/markrgba-css/nvue/padding.css';//只引入内边距
/* #endif */
```



**使用**

就是简介图上直接添加 class 就行了。



## 3️⃣ 开发

css 生成工具：[https://www.markrgba.cn/#/make-css](https://www.markrgba.cn/#/make-css)

直接生成你想要的 css 添加就行。或者提交 pull request。



## English

> Fork from [https://gitee.com/CLQing/MarkrgbaCss_UniApp](https://gitee.com/CLQing/MarkrgbaCss_UniApp)

### Document

[https://docs.markrgba.cn/markrgbaCss/pc/#/introduce](https://docs.markrgba.cn/markrgbaCss/pc/#/introduce)

Generate more css class: [https://www.markrgba.cn/#/make-css](https://www.markrgba.cn/#/make-css)



### Getting Started

**Install**

```bash
npm i @limm/markrgba-css
```



**Import all components**

```javascript
import '@limm/markrgba-css/index.css'
```



**Import on demand**

```javascript
// wip
```



### Usage

In your `.vue`  files

```html
<view class="p-all-32">
    <view class="c-999 fs-32 pl-32">
        一款语义化的CSS基础库
    </view>
</view>
```



example Inline style

Good:

- easy to edit

```html
<view>
    <view style="width:500rpx;height:250rpx;padding-top:20rpx;font-size:28rpx border-radius:20rpx">
        a box
    </view>
</view>
```

Bad:

- Too many inline styles can make Html very bloated



With markrgba-css

```html
<view>
	<view class="w-500 h-250 pt-20 fs-28 br-20">一个box</view>
</view>
```

If more same element

```html
<view>
    <view class="w-500 h-250 pt-20 fs-28 br-20">一个box</view>
    <view class="w-500 h-250 pt-20 fs-28 br-20">一个box</view>
    <view class="w-500 h-250 pt-20 fs-28 br-20">一个box</view>
    <view class="w-500 h-250 pt-20 fs-28 br-20">一个box</view>
    <view class="w-500 h-250 pt-20 fs-28 br-20">一个box</view>
</view>
```

Resolve

```html
<view>
    <view :class="c_box">一个box</view>
    <view :class="c_box">一个box</view>
    <view :class="c_box">一个box</view>
    <view :class="c_box">一个box</view>
    <view :class="c_box">一个box</view>
</view>
```

```javascript
export default {
  data() {
    return {
      c_box:'w-500 h-250 pt-20 fs-28 br-20'
    }
  }
}
```



### Modules

> wip

border

color

font

layout

margin

padding

other

