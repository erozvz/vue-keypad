vue-keypad
=============

![](demo.gif)

基于 Vue.js 的模拟数字键盘插件 

## 安装

```sh
npm install --save @zee.kim/vue-keypad
```

## 使用
首先在项目的入口文件中引入, 调用 Vue.use 安装。

```javascript
import vueKeypad from '@zee.kim/vue-keypad'
Vue.use(vueKeypad)
```

```HTML
<div id="app">
    <div @click="input()">${{money}}</div>
    <keypad :show="keypad.show" @input="keypad.input"></keypad>
</div>
```

```javascript
export default {
  data() {
    return {
        money:"",
        keypad:{
            show:false,
            input:(value)=>{}
        },
    },
    methods:{
        input(){
            this.keypad.show=true;
            this.keypad.input=(value)=>{
                this.money=value;
            }
        }
    }
}
```