# markrgba-css

> Fork from [https://gitee.com/CLQing/MarkrgbaCss_UniApp](https://gitee.com/CLQing/MarkrgbaCss_UniApp)



## Document

[https://docs.markrgba.cn/markrgbaCss/pc/#/introduce](https://docs.markrgba.cn/markrgbaCss/pc/#/introduce)

Generate more css class: [https://www.markrgba.cn/#/make-css](https://www.markrgba.cn/#/make-css)



## Getting Started

### Install

```bash
npm i @limm/markrgba-css
```



### Import all components

```javascript
import '@limm/markrgba-css/index.css'
```



### Import on demand

```javascript
// wip
```



## Usage

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



## Modules

> wip



### border

### color

### font

### layout

### margin

### padding

### other

