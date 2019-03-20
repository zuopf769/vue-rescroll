# vue-rescroll 是一款滚动状态管理指令化的插件。</br>Is a rolling state management instruction plug-in.

[![https://www.npmjs.com/package/vue-rescroll](https://img.shields.io/npm/v/vue-rescroll.svg?label=vue-rescroll)](https://www.npmjs.com/package/vue-rescroll)  ![总下载量](https://img.shields.io/npm/dt/vue-rescroll.svg)

## How to use it

### install
```bash
npm install vue-rescroll --save
```
### use
#### 全局注册/Global registration (main.js)
```javascript
import VueRescroll from 'vue-rescroll';
Vue.use(VueRescroll);
```
#### 局部注册/Partial registration (*.vue)
```javascript
import { directive } from 'vue-rescroll';
directives: {
    'rescroll': directive
}
```
#### *.vue
##### 使用默认配置/use default config
```javascript
<div v-rescroll="{name: 'A unique marker'}"></div>
```
#### 参数配置/Parameter configuration
* name(string): 必传，用来保存滚动状态的key值。  
name: required,the key value used to save the scrolling state.
* type(string): 滚动类型(局部，全局)。
type: 
```html
<img :src="baseUrl" v-img-lazy-load="{url: ''}" />
```
### tips
页面不要使用keep-alive缓存，那样的话，钩子函数不会触发。</br>
Don't use keep-alive caching for your pages. In that case, the hook function won't trigger</br>

使用vuex缓存数据/use vuex
```javascript
async created () {
    if (hasData) return hasData;
    return await this.getData();
}
```
必须要每次刷新的页面/must refreshed
```javascript
async created () {
    openLoading();
    await this.getData();
    closeLoading();
}
```
[详细描述各种现象博客地址](https://blog.csdn.net/theoneEmperor/article/details/82669022)
