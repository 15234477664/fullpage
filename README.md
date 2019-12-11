# fullpage
Vue中使用fullpage.js

## 安装
```js
npm install vue-fullpage.js
```
## 入口文件main.js
```js
import 'fullpage.js/vendors/scrolloverflow';
import VueFullPage from 'vue-fullpage.js';
Vue.use(VueFullPage);
```
## 页面中使用
```html
<template>
    <div>
        <full-page :options="options">
            <div class="section">
                <div class="box1">
                   section1
                </div>
            </div>
            <div class="section">
                <div class="box2">
                section2
                </div>
            </div>
            <div class="section">
                <div class="box3">
                section3
                </div>
            </div>
        </full-page>
    </div>
</template>
```
```js
export default {
    name: '',
    data () {
        return {
            options: {
                licenseKey: 'OPEN-SOURCE-GPLV3-LICENSE',
                afterLoad: this.afterLoad,
                scrollOverflow: true,
                scrollBar: false,
                menu: '#menu',
                // navigation: true,
                // anchors: ['page1', 'page2', 'page3'],
                sectionsColor: ['#41b883', '#ff5f45', '#0798ec', '#fec401', '#1bcee6', '#ee1a59', '#2c3e4f', '#ba5be9', '#b4b8ab']
            }
        }
    }
}
```
运行后控制台会报如下的错误：

![Image text](https://github.com/15234477664/fullpage/blob/master/1.jpg)

解决方案如下：



