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

![Image text](https://github.com/15234477664/fullpage/blob/master/2.jpg)

![Image text](https://github.com/15234477664/fullpage/blob/master/3.jpg)

![Image text](https://github.com/15234477664/fullpage/blob/master/4.jpg)

![Image text](https://github.com/15234477664/fullpage/blob/master/5.jpg)

![Image text](https://github.com/15234477664/fullpage/blob/master/6.jpg)

## 使用参数如下：
```js
//为每个section设置背景色
sectionsColor: ["#f00","#0f0","#00f"],
//用来控制slide幻灯片的箭头，设置为false，两侧的箭头会消失
controlArrows: false,
//每一页幻灯片的内容是否垂直居中
verticalCentered: false,
//字体是否随着窗口缩放而缩放
resize: true,
//页面滚动速度
scrollingSpeed: 700,
//定义锚链接，用户可以快速打开定位到某一页面；不需要加"#"，不要和页面中任意的id和name相同
anchors: ["page1","page2","page3"],
//是否锁定锚链接
lockAnchors: true,
//定义section页面的滚动方式，需要引入jquery.easings插件
easing:,
//是否使用css3 transform来实现滚动效果
css3: false,
//滚动到最顶部后是否连续滚动到底部
loopTop: true,
//滚动到最底部后是否连续滚动到顶部
loopBottom: true,
//横向slide幻灯片是否循环滚动
loopHorizontal: false,
 //是否循环滚动，不会出现跳动，效果很平滑
 continuousVertical: true,
 //是否使用插件滚动方式，设为false后，会出现浏览器自带的滚动条，将不会按页滚动
 autoScrolling: false,
 //是否包含滚动条，设为true，则浏览器自带的滚动条会出现，页面还是按页滚动，但是浏览器滚动条默认行为也有效
 scrollBar: true,
 //设置每个section顶部的padding，当我们要设置一个固定在顶部的菜单、导航、元素等时使用
 paddingTop: "100px",
 //设置每个section底部的padding，当我们要设置一个固定在底部的菜单、导航、元素等时使用
 paddingBottom: "100px",
 //固定的元素，为jquery选择器；可用于顶部导航等
 fixedElements: ".nav",
 //是否可以使用键盘方向键导航
 keyboardScrolling: false,
 //在移动设置中页面敏感性，最大为100，越大越难滑动
 touchSensitivity: 5,
 //设为false，则通过锚链接定位到某个页面不再有动画效果
 animateAnchor: false,
 //是否记录历史，可以通过浏览器的前进后退来导航
 recordHistory: true,
 //绑定菜单，设定相关属性和anchors的值对应后，菜单可以控制幻灯片滚动
 menu: '.nav',
 //是否显示导航，设为true会显示小圆点作为导航
 navigation: true,
 //导航小圆点的位置，可以设置为left或者right
 navigationPosition: right,
 //鼠标移动到小圆点上时显示出的提示信息
 navigationTooltips: ["第一页","第二页","第三页"],
 //是否显示当前页面小圆点导航的提示信息，不需要鼠标移上
 showActiveTooltip: true,
 //是否显示横向幻灯片的导航
 slidesNavigation: true,
 //横向幻灯片导航的位置，可以为top或者bottom
 slidesNavPosition: bottom,
 //内容超过满屏时是否显示滚动条，需要jquery.slimscroll插件
 scrollOverflow: true,
 //section选择器
 sectionSelector: ".section",
 //slide选择器
 slideSelector: ".slide"
 
licenseKey: 'OPEN-SOURCE-GPLV3-LICENSE',
afterLoad: this.afterLoad,
scrollOverflow: true,
navigation: true,//是否显示导航，默认为false
navigationPosition: 'right',//导航小圆点的位置
scrollBar: false,
keyboardScrolling: false,//是否可以使用键盘方向键导航，默认为true
continuousVertical: true, /// 是否循环滚动，默认为false。如果设置为true，则页面会循环滚动，而不像loopTop或loopBottom那样出现跳动，注意这个属性和loopTop、loopBottom不兼容和，不要同时设置
menu: '#menu',
// navigation: true,
// anchors: ['page1', 'page2', 'page3'],
sectionsColor: ['#41b883', '#ff5f45', '#0798ec', '#fec401', '#1bcee6', '#ee1a59', '#2c3e4f', '#ba5be9', '#b4b8ab']

click() {
    // vue调用fullpapge的方法
    this.$refs.page.api.moveSectionDown();
    // moveSectionDown();
}

 // 向上滚动一页
 moveSectionUp();
 //向下滚动一页
 moveSectionDown();
 //滚动到第几页，第几个幻灯片；页面从1计算，幻灯片从0计算
 moveTo(wection,slide);
 //和moveTo一样，但是没有动画效果
 silentMoveTo(section,slide);
 //幻灯片向右滚动
 moveSlideRight();
 //幻灯片向左滚动
 moveSlideLeft();
 //动态设置autoScrolling配置项
 setAutoScrolling(boolean);
 //动态设置lockAnchors配置项
 setLockAnchors(boolean);
 //动态设置recordHistory配置项
 setRecordHistory(boolean);
 //动态设置scrollingSpeed配置项
 setScrollingSpeed(milliseconds);
 //添加或删除鼠标/滑动控制，第一个参数为启用、禁用；第二个参数为方向，取值包含all、up、dowm、left、right，可以使用多个，逗号分隔
 setAllowScrolling(boolean,[directions]);
 //销毁fullpage特效，不写type，fullpage给页面添加的样式和html元素还在；如果使用all，则样式和html等全部被销毁
 destroy(type);
 //重新更新页面和尺寸，用于通过ajax请求后改变了页面结构之后，重建效果
 reBuild();

```

