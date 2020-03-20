# VUE

## 1. VUE 基础

### 1.1 VUE简介

- Javascript 框架
- 简化 DOM 操作
- 响应式数据操作

### 1.2 第一个 [VUE ](https://cn.vuejs.org/)程序

```html
<body>
<div id="app">
    {{ message }}
</div>
<script src="./vue.js"></script>
<script>
    var app = new Vue({
        el: "#app",
        data: {
            message: "Hello Vue!"
        }
    })
</script>
</body>
```

### 1.3 el:挂载点

```html
<body>
{{ message }}
<div id="app" class="app">
    {{ message }}
    <span> {{ message }} </span>
</div>
<!--<p id="app" class="app">-->
    <!--{{ message }}-->
    <!--<span> {{ message }} </span>-->
<!--</p>-->
<script src="./vue.js"></script>
<script>
    var app = new Vue({
        el: "#app",
        // el: ".app",
        // el: "div",
        data: {
            message: "黑马程序员"
        }
    })
</script>
</body>
```

- el 用来设置 Vue 实例挂载（管理）的元素
- Vue 会管理 el 选项**命中的元素**及其内部的**后代元素**
- 可以使用其它的选择器，但是建议使用 **ID选择器**
- 可以使用其它的双标签，不能使用 **html 和 body**

### 1.4 data:数据对象

```html
<body>
<div id="app" class="app">
    {{ message }}
    <h2> {{ school.name }} {{ school.mobile }} </h2>
    <ul>
        <li>{{ campus[0] }}</li>
        <li>{{ campus[1] }}</li>
        <li>{{ campus[2] }}</li>
        <li>{{ campus[3] }}</li>
    </ul>
</div>
<script src="./vue.js"></script>
<script>
    var app = new Vue({
        el: "#app",
        data: {
            message: "你好 小黑！",
            school: {
                name: "黑马程序员",
                mobile: "400-618-9090"
            },
            campus: ["北京校区", "上海校区", "广州校区", "深圳校区"]
        }
    })
</script>
</body>
```

- Vue 中用到的数据定义在 **data** 中
- data 中可以写**复杂数据类型**的数据
- 渲染复杂数据类型数据时，遵守 **js 的语法***即可

## 2. 本地应用

### 2.1 内容绑定，事件绑定

#### 2.1.1 v-text

设置标签的文本值（textContent）

**语法：**

```html
<div id="app">
	<h2 v-text="message"></h2>
</div>
```

```js
var app = new Vue({
    el: "#app",
    data：{
    	message: "黑马程序员"
	}
})
```

**实例：**

```html
<body>
<div id="app" class="app">
    <h2 v-text="message + '!'">深圳</h2>
    <h2 v-text="info + '!'">深圳</h2>
    <h2>{{ message + '!'}}深圳</h2>
</div>
<script src="./vue.js"></script>
<script>
    var app = new Vue({
        el: "#app",
        data: {
            message: "黑马程序员",
            info: "前端与移动教研部"
        }
    })
</script>
</body>
```

- v-text 指令的作用是：设置标签的内容（text Content）
- 默认写法会替换全部内容，使用 **差值表达式{{}}** 可以替换指定内容
- 内部支持写**表达式**

#### 2.1.2 v-html

设置标签的 innerHTML

**语法：**

```html
<div id="app">
	<p v-html="content"></p>
</div>
```

```js
var app = new Vue({
    el: "#app",
   	data: {
        content: "<a href='http://www.baidu.com'>百度</a>"
    }
})
```

**实例：**

```html
<body>
<div id="app">
    <p v-html="content"></p>
    <p v-text="content"></p>
</div>
<script src="vue.js"></script>
<script>
    var app = new Vue({
        el: "#app",
        data: {
            // content: "黑马程序员"
            content: "<a href='http://www.baidu.com'>百度</a>"
        }

    })
</script>
</body>
```

- v-html 指令的作用是：设置元素的 **innerHTML**
- 内容中有 **html** 结构会被解析为 **标签**
- **v-text** 指令无论内容是什么，只会解析为 **文本**
- 解析文本使用 **v-text**，需要解析 **html** 结构使用 **v-html**

#### 2.1.3 v-on 基础

为元素绑定事件

**语法：**

```html
<div id="app">
	<input type="button" value="事件绑定" v-on:click="dolt">
    <input type="button" value="事件绑定" v-on:mouseenter="dolt">
    <input type="button" value="事件绑定" v-on:dblclick="dolt">
    <input type="button" value="事件绑定" @dblclick="dolt">
</div>
```

```js
var app = new Vue({
    el: "#app",
    methods： {
    	dolt: function() {
    		// 逻辑
		}
	}
})
```

**实例：**

```html
<body>
<div id="app">
    <input type="button" value="v-on指令" v-on:click="doIt">
    <input type="button" value="v-on简写" @click="doIt">
    <input type="button" value="双击事件" @dblclick="doIt">
    <h2 @click="changeFood">{{ food }}</h2>
</div>
<script src="vue.js"></script>
<script>
    var app = new Vue({
        el: "#app",
        data: {
            food: "西兰花炒蛋"
        },
        methods: {
            doIt: function () {
                alert("做IT");
            },
            changeFood: function () {
                // console.log(this.food);
                this.food += "好好吃！"
            }
        }
    })
</script>
</body>
```

- **v-on** 指令的作用是：为元素绑定事件
- 事件名不需要写 **on**
- 指令可以简写为 **@**
- 绑定的方法定义在 **methods** 属性中
- 方法内部通过 **this** 关键字可以访问定义在 **data** 中的数据

#### 2.1.4 实例：计数器

```css
* {
    margin: 0;
    padding: 0;
}
button {
    border: none;
    outline: none;
}
.input-num {
    display: flex;
    position: absolute;
    left: 50%;
    top: 50%;
    width: 300px;
    height: 60px;
    border: 1px solid #ddd;
    line-height: 60px;
    border-radius: 10px;
    overflow: hidden;
    transform: translate(-50%, -50%);
}
.input-num button {
    flex: 30%;
    color: #ff0000;
    font-size: 25px;
    background-color: #ddd;
}
.input-num span {
    flex: 40%;
    font-size: 25px;
    text-align: center;
}
```

```html
<body>
<div id="app">
    <!--计数器功能区域-->
    <div class="input-num">
        <button @click="sub">-</button>
        <span>{{ num }}</span>
        <button @click="add">+</button>
    </div>
</div>
<script src="vue.js"></script>
<script>
    var app = new Vue({
        el: "#app",
        data: {
            num: 1
        },
        methods: {
            add: function () {
                // console.log("add");
                if(this.num < 10) {
                    this.num++;
                } else {
                    alert("别点了，最大了！");
                }
            },
            sub: function () {
                // console.log("sub");
                if(this.num > 0) {
                    this.num--;
                } else {
                    alert("别点了，最小了！");
                }
            }
        }
    })
</script>
</body>
```

### 2.2 显示切换，属性绑定

#### 2.2.1 v-show

根据表达式的真假，切换元素的显示和隐藏

**语法：**

```html
<div id="app">
    <img src="地址" v-show="true">
    <img src="地址" v-show="isShow">
    <img src="地址" v-show="age >= 18">
</div>
```

```js
var app = new Vue({
    el: "#app",
    data: {
        isShow: true,
        age: 16
    }
})
```

**实例：**

```html
<body>
<div id="app">
    <input type="button" value="切换显示状态" @click="changeIsShow">
    <input type="button" value="累加年龄" @click="addAge">
    <img v-show="isShow" src="./beibei.jpg" alt="beibei">
    <img v-show="age>=18" src="./beibei.jpg" alt="beibei">
</div>
<script src="vue.js"></script>
<script>
    var app = new Vue({
        el: "#app",
        data: {
            isShow: false,
            age: 17
        },
        methods: {
            changeIsShow: function () {
                this.isShow = !this.isShow;
            },
            addAge: function () {
                this.age++;
            }
        }
    })
</script>
</body>
```

- **v-show** 指令的作用是：根据真假切换元素的显示状态
- 原理是修改元素的 **display**，实现显示隐藏
- 指令后面的内容，最终都会解析为 **布尔值**
- 值为 **true** 元素显示，值为 **false** 元素隐藏
- 数据改变之后，对应元素的显示状态会 **同步更新**

#### 2.2.2 v-if

根据表达式的真假，切换元素的显示和隐藏（操作 dom 元素）

**语法：**

```html
<div id="app">
    <p v-if="true">我是一个 P 标签</p>
    <p v-if="isShow">我是一个 P 标签</p>
</div>
```

```js
var app = new Vue({
    el: "#app",
    data: {
        isShow: false
    }
})
```

**实例：**

```html
<body>
<div id="app">
    <input type="button" value="切换显示" @click="toggleIsShow">
    <p v-if="isShow">黑马程序员</p>
    <p v-show="isShow">黑马程序员 - v-show 修饰</p>
    <h2 v-if="temperature>=35">热死啦</h2>
</div>
<script src="vue.js"></script>
<script>
    var app = new Vue({
        el: "#app",
        data: {
            isShow: false,
            temperature: 40
        },
        methods: {
            toggleIsShow: function () {
                this.isShow = !this.isShow;
            }
        }
    })
</script>
</body>
```

- v-if 指令的作用是：根据表达式的真假切换元素的显示状态
- 本质是通过操作 dom 元素来切换显示状态
- 表达式的值为 true，元素存在于 dom 树中，为 false，从 dom 树中移除
- 频繁的切换 v-show，反之使用 v-if，前者的切换消耗小

#### 2.2.3 v-bind

设置元素的属性（比如：src，title，class）

**语法：**

```html
<div id="app">
    <img v-bind:src="地址">
    <img v-bind:title="imgTitle + '!!!'">
    <img v-bind:class="isActive?'active':''">
    <img v-bind:class="{active: isActive}">
    <img :class="{active: isActive}">
</div>
```

```js
var app = new Vue({
    el: "#app",
    data: {
        imgSrc: "图片地址",
        imgTitle: "黑马程序员",
        isActive: false
    }
})
```

**实例：**

```css
.active {
    border: 1px solid #f00;
}
```

```html
<body>
<div id="app">
    <img v-bind:src="imgSrc" alt="">
    <br>
    <img :src="imgSrc" alt="" :title="imgTitle+'!!!'" :class="isActive?'active':''" @click="toggleActive">
    <br>
    <img :src="imgSrc" alt="" :title="imgTitle+'!!!'" :class="{active: isActive}" @click="toggleActive">
</div>
<script src="vue.js"></script>
<script>
    var app = new Vue({
        el: "#app",
        data: {
            imgSrc: "https://ss0.bdstatic.com/94oJfD_bAAcT8t7mm9GUKT-xh_/timg?image&quality=100&size=b4000_4000&sec=1584586262&di=cdce41ef4b0437c74646f3bf7dbdb68e&src=http://a0.att.hudong.com/78/52/01200000123847134434529793168.jpg",
            imgTitle: "黑马程序员",
            isActive: false
        },
        methods: {
            toggleActive: function () {
                this.isActive = !this.isActive;
            }
        }
    })
</script>
</body>
```

- **v-bind** 指令的作用是：为元素绑定属性
- 完整写法是：**v-bind:属性名**
- 简写的话可以直接省略 **v-bind**，只保留 **:属性名**
- 需要动态的增删 **class** 建议使用对象的方式

#### 2.2.4 实例：图片切换

```css
* {
    margin: 0;
    padding: 0;
}
.center {
    position: absolute;
    left: 50%;
    top: 50%;
    width: 1366px;
    height: 768px;
    background-color: #f00;
    transform: translate(-50%, -50%);
}
.center a {
    display: block;
    width: 40px;
    height: 100px;
    top: 50%;
    transform: translateY(-50%);
    overflow: hidden;
}
.center a img {
    display: block;
    width: 100%;
    height: 100%;
}
.center .left {
    position: absolute;
    left: 10px;
}
.center .right {
    position: absolute;
    right: 10px;
}
```

```html
<body>
<div id="mask">
    <div class="center">
        <img :src="imgArr[index]" alt="">
        <a href="javascript:;" class="left" @click="prev" v-show="index!==0">
            <img src="./img/left_03.png" alt="">
        </a>
        <a href="javascript:;" class="right" @click="next" v-show="index!==imgArr.length-1">
            <img src="./img/right_03.png" alt="">
        </a>
    </div>
</div>
<script src="vue.js"></script>
<script>
    var app = new Vue({
        el: "#mask",
        data: {
            imgArr: [
                "./img/img%20(1).jpg",
                "./img/img%20(2).jpg",
                "./img/img%20(3).jpg",
                "./img/img%20(4).jpg"
            ],
            index: 0
        },
        methods: {
            prev: function() {
                this.index--;
            },
            next: function () {
                this.index++;
            }
        }
    })
</script>
</body>
```

- 列表数据使用 **数组** 保存
- v-bind 指令可以设置元素属性，比如 src
- v-show 和 v-if 都可以切换元素的显示状态，频繁切换用 v-show

### 2.3 列表循环，表单元素绑定

#### 2.3.1 v-for

根据数据生成列表结构

**语法：**

```html
<div id="app">
    <ul>
        <li v-for="(item,index) in arr" :title="item">
            {{ index }}{{ item }}
        </li>
        <li v-for="(item,index) in objArr">
            {{ item.name }}
        </li>
    </ul>
</div>
```

```js
var app = new Vue({
    el: "#app",
    data: {
        arr: [1, 2, 3, 4, 5],
        objArr: [
            {name: "jack"},
            {name: "rose"}
        ]
    }
})
```

**实例：**

```html
<body>
<div id="app">
    <input type="button" value="添加数据" @click="add">
    <input type="button" value="移除数据" @click="remove">
    <ul>
        <li v-for="(item,index) in arr">
            {{ index+1 }}黑马程序员校区：{{ item }}
        </li>
    </ul>
    <h2 v-for="(item, index) in vegetables" :title="item.name ">
        {{ item.name }}
    </h2>
</div>
<script src="vue.js"></script>
<script>
    var app = new Vue({
        el: "#app",
        data: {
            arr: ["北京", "上海", "广州", "深圳"],
            vegetables: [
                {name: "西红柿炒鸡蛋"},
                {name: "土豆炖牛腩"}
            ]
        },
        methods: {
            add: function () {
                this.vegetables.push({name: "爆炒猪肝"});
            },
            remove: function () {
                this.vegetables.shift();
            }
        }
    })
</script>
</body>
```

- **v-for** 指令的作用是：根据数据生成列表结构
- 数组经常和 **v-for** 结合使用
- 语法是 **(item, index) in 数据** 
- item 和 index 可以结合其它指令一起使用
- 数组长度的更新会同步到页面上，是响应式的

#### 2.3.2 [v-on 补充](https://cn.vuejs.org/v2/api/#v-on)

传递自定义参数，事件修饰符

**语法：**

```html
<div id="app">
    <input type="button" @click="doIt(p1, p2)" />
    <input type="text" @keyup.enter="sayHi" />
</div>
```

```js
var app = new Vue({
    el: "#app",
    methods: {
        doIt: function(p1, p2) {
            
        },
        sayHi: function() {}
    }
})
```

**实例：**

```html
<body>
<div id="app">
    <input type="button" value="点击" @click="doIt('good', 'idea')" />
    <input type="text" @keyup.enter="sayHi" />
</div>
<script src="vue.js"></script>
<script>
    var app = new Vue({
        el: "#app",
        data: {

        },
        methods: {
            doIt: function (p1, p2) {
                console.log("做IT");
                console.log(p1);
                console.log(p2);
            },
            sayHi() {
                alert("吃了没");
            }
        }
    })
</script>
</body>
```

- 事件绑定的方法写成 **函数调用** 的形式，可以传入自定义参数
- 定义方法的时候需要定义**形参**来接收传入的实参
- 事件的后面跟上 **.修饰符** 可以对事件进行限制
- **.enter** 可以限制触发的按键为回车
- 事件修饰符有多种

#### 2.3.3 v-model

获取和设置表单元素的值（**双向数据绑定**）

**语法：**

```html
<div id="app">
    <input type="text" v-model="message"/>
</div>
```

```js
var app = new Vue({
    el: "#app",
    data: {
        message: "黑马程序员"
    },
    methods: {
        
    }
})
```

- **v-model** 指令的作用是便捷的设置和获取表单元素的值
- 绑定的数据会和表单元素值相关联
- 绑定的数据和表单元素的值双向绑定

#### 2.3.4 实例：小黑记事本

```css
* {
    margin: 0;
    padding: 0;
}
ul, ol {
    list-style: none;
}
input, button {
    border: none;
    outline: none;
}
input::-webkit-input-placeholder {
    color: #dddddd;
    font-style: italic;
}
#todoapp {
    margin: 20px auto;
    width: 500px;
    box-shadow: 0 3px 15px rgba(0, 0, 0, .1);
}
.header h1 {
    padding: 40px 0;
    color: #f00;
    font-size: 40px;
    font-weight: 400;
    text-align: center;
    background-color: #0ff;
}
.header input {
    width: 100%;
    height: 60px;
    border: 1px solid #eee;
    padding-left: 20px;
    color: #666;
    font-size: 25px;
    box-sizing: border-box;
}
.main {
    border: 1px solid #eee;
    border-bottom: none;
    border-top: none;
}
.todo {
    border-bottom: 1px solid #eee;
}
.todo .view {
    height: 60px;
    padding: 0 10px;
    line-height: 60px;
    font-size: 25px;
}
.todo .view .index {
    font-size: 18px;
    vertical-align: 2px;
    color: #999;
}
.todo .view label {
    margin-left: 30px;
    color: #666;
}
.todo:hover .view a {
    display: inline-block;
}
.todo .view a {
    display: none;
    position: relative;
    float: right;
    margin-top: 20px;
    margin-right: 10px;
    width: 16px;
    height: 16px;
}
.todo .view a::before {
    content: "";
    position: absolute;
    left: 0;
    top: 0;
    height: 16px;
    width: 2px;
    background-color: #f1a899;
    transform: rotate(-45deg);
}
.todo .view a::after {
    content: "";
    position: absolute;
    left: 0;
    top: 0;
    height: 16px;
    width: 2px;
    background-color: #f1a899;
    transform: rotate(45deg);
}
.footer {
    height: 40px;
    border: 1px solid #eee;
    border-top: none;
    padding: 0 10px;
    line-height: 40px;
    color: #999;
    font-size: 12px;
}
.footer .clear-completed {
    float: right;
    height: 100%;
    background-color: #fff;
    color: #999;
}
```

```html
<body>
<section id="todoapp">
    <header class="header">
        <h1>小兰记事本</h1>
        <input type="text" v-model="inputValue" @keyup.enter="add" autofocus="autofocus" autocomplete="off" placeholder="请输入任务" class="new-todo" />
    </header>
    <section class="main">
        <ul class="todo-list">
            <li class="todo" v-for="(item, index) in list">
                <div class="view">
                    <span class="index">{{ index + 1 }}.</span>
                    <label>{{ item }}</label>
                    <a href="javascript:;" class="destory" @click="remove(index)"></a>
                </div>
            </li>
        </ul>
    </section>
    <footer class="footer">
        <span class="todo-count" v-if="list.length !== 0">
            <strong>{{ list.length }}</strong>
            items left
        </span>
        <button @click="clear" v-if="list.length !== 0" class="clear-completed" >Clear</button>
    </footer>
</section>
<script src="vue.js"></script>
<script>
    var app = new Vue({
        el: "#todoapp",
        data: {
            inputValue: "",
            list: ["写代码", "吃饭饭", "睡觉觉"]
        },
        methods: {
            add: function () {
                this.list.push(this.inputValue)
            },
            remove: function (index) {
                this.list.splice(index, 1);
            },
            clear: function () {
                this.list = [];
            }
        }
    })
</script>
</body>
```

## 3. 网络应用

Vue 结合网络数据开发应用

### 3.1 [axios](http://www.axios-js.com/)

功能强大的网络请求库

`<script src="https://unpkg.com/axios/dist/axios.min.js"></script>`

**语法：**

```js
// GET
axios.get('/user?ID=12345')
	.then(function (response) {
		console.log(response);
	})
	.catch(function (error) {
		console.log(error);
	});
axios.get('/user', {
    params: {
        ID: 12345
    }
})
    .then(function (response) {
		console.log(response);
	})
    .catch(function (error) {
		console.log(error);
	});
```

```js
// POST
axios.post('/user', {
	firstName: 'Fred',
	lastName: 'Flintstone'
})
	.then(function (response) {
		console.log(response);
	})
	.catch(function (error) {
		console.log(error);
	});
```

**实例：**

```html
<body>
<input type="button" value="get请求" class="get">
<input type="button" value="post请求" class="post">
<script src="https://unpkg.com/axios/dist/axios.min.js"></script>
<script>
    window.addEventListener("load", function() {
        document.querySelector(".get").onclick = function () {
            axios.get("https://autumnfish.cn/api/joke/list?num=3")
                .then(function (response) {
                    console.log(response);
                })
                .catch(function (err) {
                    console.log(err);
                })
        };

        document.querySelector(".post").onclick = function () {
            axios.post("https://autumnfish.cn/api/user/reg", {
                username: "milla"
            })
                .then(function (response) {
                    console.log(response);
                })
                .catch(function (err) {
                    console.log(err);
                })
        }
    })
</script>
</body>
```

- **axios** 必须先导入才可以使用
- 使用 **get** 或 **post** 方法即可发送对应的请求
- **then** 方法中的回调函数会在请求成功时触发
- **catch** 方法用来捕获异常
- 通过回调函数的形参可以获取响应内容，或错误信息

### 3.2 axios+vue

axios 如何结合 vue 开发网络应用

**实例：**

```html
<body>
<div id="app">
    <input type="button" value="获取笑话" @click="getJoke">
    <p>{{ joke }}</p>
</div>
<script src="https://unpkg.com/axios/dist/axios.min.js"></script>
<script src="./vue.js"></script>
<script>
    var app = new Vue({
        el: "#app",
        data: {
            joke: "好笑的笑话"
        },
        methods: {
            getJoke: function () {
                var that = this;
                axios.get("https://autumnfish.cn/api/joke")
                    .then(function (response) {
                        // console.log(response);
                        // console.log(response.data);
                        that.joke = response.data;
                    })
                    .catch(function (err) {
                        console.log(err);
                    })
            }
        }
    })
</script>
</body>
```

- **axios** 回调函数中的 **this** 已经改变，无法访问到 **data** 中的数据
- 把 **this** 保存起来，回调函数中直接使用保存的 **this** 即可
- 和本地应用最大的区别就是改变了 **数据来源**

### 3.3 实例：天知道

```html
<body>
<div id="app" class="wrap">
    <div class="search_form">
        <div class="logo"><img src="./img/logo_03.png" alt=""></div>
        <div class="form_group">
            <input @keyup.enter="searchWeather" v-model="city" type="text" class="input_txt" placeholder="请输入查询的城市" />
            <button @click="searchWeather" class="input_sub">Search</button>
        </div>
        <div class="hotkey">
            <a @click="changeCity('北京')" href="javascript:;">北京</a>
            <a @click="changeCity('上海')" href="javascript:;">上海</a>
            <a @click="changeCity('广州')" href="javascript:;">广州</a>
            <a @click="changeCity('深圳')" href="javascript:;">深圳</a>
            <a @click="changeCity('西安')" href="javascript:;">西安</a>
        </div>
    </div>
    <ul class="weather_list">
        <li v-for="(item, index) in weatherList">
            <div class="info_type"><span>{{ item.type }}</span></div>
            <div class="info_temp">
                <b>{{ item.low }}</b>
                ~
                <b>{{ item.high }}</b>
            </div>
            <div class="info_date"><span>{{ item.date }}</span></div>
        </li>
    </ul>
</div>
<script src="https://unpkg.com/axios/dist/axios.min.js"></script>
<script src="./js/vue.js"></script>
<script src="./js/main.js"></script>
</body>
```

```css
* {
    margin: 0;
    padding: 0;
}
ul {
    list-style: none;
}
input, button {
    border: none;
    outline: none;
}
a {
    text-decoration: none;
}
b {
    font-weight: 400;
}
.wrap {
    width: 1000px;
    margin: 0 auto;
}
.wrap .search_form {
    width: 670px;
    margin: 100px auto 10px;
}
.wrap .search_form .logo {
    width: 200px;
    height: 70px;
    margin: 0 auto 100px;
}
.wrap .search_form .logo img {
    display: block;
    width: 100%;
    height: 100%;
}
.wrap .search_form .form_group .input_txt {
    width: 600px;
    height: 35px;
    padding-left: 10px;
    border: 1px solid #00a4ff;
    box-sizing: border-box;
}
.wrap .search_form .form_group .input_sub {
    margin-left: -5px;
    width: 70px;
    height: 35px;
    background-color: #00a4ff;
    vertical-align: bottom;
}
.wrap .search_form .hotkey a{
    color: #666;
    font-size: 12px;
    padding-left: 5px;
}
.weather_list {
    display: flex;
    margin-top: 50px;
}
.weather_list li {
    flex: 1;
    position: relative;
}
.weather_list li::after {
    content: "";
    position: absolute;
    right: 0;
    top: 0;
    width: 1px;
    height: 100%;
    background: linear-gradient(
            to bottom,
            rgba(200,200,200,0) 0%,
            rgba(200,200,200,0) 10%,
            rgba(200,200,200,0.3) 20%,
            rgba(200,200,200,0.4) 30%,
            rgba(200,200,200,0.5) 40%,
            rgba(200,200,200,0.8) 50%,
            rgba(200,200,200,0.5) 60%,
            rgba(200,200,200,0.4) 70%,
            rgba(200,200,200,0.3) 80%,
            rgba(200,200,200,0) 90%,
            rgba(200,200,200,0) 100%)
}
.weather_list li:last-child::after {
    width: 0;
}
.info_type {
    margin-bottom: 15px;
    color: #FFA500;
    font-size: 35px;
    text-align: center;
}
.info_temp {
    margin-bottom: 15px;
    color: #FFA500;
    font-size: 14px;
    text-align: center;
}
.info_date {
    color: #999;
    font-size: 16px;
    text-align: center;
}
```

```js
window.addEventListener("load", function () {
    var app = new Vue({
        el: "#app",
        data: {
            city: "",
            weatherList: []
        },
        methods: {
            searchWeather: function () {
                var that = this;
                axios.get("http://wthrcdn.etouch.cn/weather_mini?city=" + that.city)
                    .then(function (response) {
                        that.weatherList = response.data.data.forecast;
                    })
                    .catch(function (err) {
                        console.log(err);
                    })
            },
            changeCity: function (city) {
                this.city = city;
                this.searchWeather();
            }

        }
    }) 
});
```

## 4. [综合应用-MusicPlayer](https://github.com/millaCheung/musicPlayer)

```html
<body>
<div class="wrap">
    <!--播放器主体区域-->
    <div class="play_wrap" id="player">
        <div class="search_bar">
            <img src="./images/player_title.png" alt="" />
            <!--搜索歌曲-->
            <div class="search_item">
                <input type="text" autocomplete="off" placeholder="五月天" v-model="query" @keyup.enter="searchMusic" />
                <a href="javascript:;" class="search_btn" @click="searchMusic"></a>
            </div>
        </div>
        <div class="center_con">
            <!--搜索歌曲列表-->
            <div class="song_wrapper">
                <ul class="song_list">
                    <li v-for="(item, index) in musicList">
                        <a href="javascript:;" @click="playMusic(item.id), play"></a>
                        <b v-text="item.name"></b>
                        <span v-if="item.mvid !== 0" @click="playMV(item.mvid)"></span>
                    </li>
                </ul>
            </div>
            <!--歌曲信息容器-->
            <div class="player_wrapper">
                <img src="./images/line.png" alt="" />
                <div class="player_con">
                    <img src="./images/player_bar.png" alt="" class="play_bar" :class="{playing: isPlaying}" />
                    <img src="./images/disc.png" class="disc autoRotate" :class="{playing: isPlaying}" />
                    <img :src="picUrl" class="cover autoRotate" :class="{playing: isPlaying}" />
                </div>
                <img src="./images/line.png" alt="" />
            </div>
            <div class="comment_wrapper">
                <h5 class="title">热门留言</h5>
                <div class="comment_list">
                    <dl v-for="(item, index) in hotComments">
                        <dt><img :src="item.user.avatarUrl" alt=""></dt>
                        <dd v-text="item.user.nickname"></dd>
                        <dd v-text="item.content"></dd>
                    </dl>
                </div>
            </div>
        </div>
        <div class="audio_con">
            <audio :src="musicUrl" @play="play" @pause="pause" controls="controls" autoplay="autoplay" loop="loop" class="myaudio"></audio>
        </div>
        <div class="video_con" v-show="isShow" style="display: none;">
            <video :src="mvUrl" controls="controls" autoplay="autoplay"></video>
            <div class="mask" @click="hide"></div>
        </div>
    </div>
</div>
<script src="https://unpkg.com/axios/dist/axios.min.js"></script>
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
<script src="https://cdnjs.cloudflare.com/ajax/libs/video.js/7.3.0/video.min.js"></script>
<script src="./js/index.js"></script>
</body>
```

```css
* {
    margin: 0;
    padding: 0;
}
input {
    border: none;
    outline: none;
}
b {
    font-weight: 400;
}
::-webkit-scrollbar {
    /*隐藏滚轮*/
    display: none;
}
.wrap {
    position: fixed;
    left: 0;
    top: 0;
    width: 100%;
    height: 100%;
    background: url("../images/bg.jpg");
    background-size: 100% 100%;
}
.play_wrap {
    position: fixed;
    left: 50%;
    top: 50%;
    width: 800px;
    height: 544px;
    margin-left: -400px;
    margin-top: -272px;
    border-radius: 5px;
    overflow: hidden;
}
.search_bar {
    position: relative;
    width: 100%;
    height: 60px;
    background-color: #1eacda;
    z-index: 9999;
}
.search_bar img {
    display: block;
    position: absolute;
    left: 20px;
    top: 50%;
    transform: translateY(-50%);
}
.search_bar .search_item {
    position: absolute;
    right: 20px;
    top: 50%;
    transform: translateY(-50%);
}
.search_bar .search_item input {
    width: 260px;
    height: 36px;
    padding-left: 20px;
    background: rgba(255, 255, 255, .4);
    border-radius: 18px;
}
.search_bar .search_item .search_btn {
    display: block;
    position: absolute;
    right: 10px;
    top: 50%;
    width: 20px;
    height: 20px;
    background: url("../images/zoom.png") no-repeat;
    transform: translateY(-50%);
}
.center_con {
    display: flex;
    height: 435px;
    background-color: rgba(255, 255, 255, .3);
}
.song_wrapper {
    flex: 25%;
    padding: 10px;
    box-sizing: border-box;
    overflow-y: scroll;
}
.song_wrapper .song_list li {
    height: 36px;
    background-color: rgba(255, 255, 255, .2);
    padding: 0 30px 0 10px;
    line-height: 36px;
    color: #333;
    font-size: 14px;
}
.song_wrapper .song_list li b {
    display: inline-block;
    width: 100px;
    margin-left: 23px;
    white-space: nowrap;
    text-overflow: ellipsis;
    overflow: hidden;
}
.song_wrapper .song_list li:nth-child(even) {
    background-color: rgba(0, 0, 0, 0);
}
.song_wrapper .song_list li a {
    display: block;
    float: left;
    margin-right: -23px;
    margin-top: 9px;
    width: 18px;
    height: 18px;
    background: url("../images/play.svg") no-repeat;
    background-size: 100% 100%;
    vertical-align: -4px;
}
.song_wrapper .song_list li span {
    display: block;
    float: right;
    margin-right: -23px;
    margin-top: 9px;
    width: 18px;
    height: 18px;
    background: url("../images/MV.svg") no-repeat;
    background-size: 100% 100%;
    vertical-align: -4px;
}
.player_wrapper {
    position: relative;
    flex: 50%;
}
.player_wrapper>img:first-child {
    float: left;
}
.player_wrapper>img:last-child {
    float: right;
}
.player_con img {
    position: absolute;
}
.player_con img.play_bar {
    left: 200px;
    top: -10px;
    z-index: 100;
    transform: rotate(-25deg);
    transform-origin: 10px 10px;
    transition: 1s;
}
.player_con img.playing {
    transform: rotate(6deg);
}
.player_con img.disc {
    left: 50%;
    top: 60px;
    z-index: 99;
    margin-left: -127px;
}
.player_con img.cover {
    left: 50%;
    top: 110px;
    height: 150px;
    width: 150px;
    z-index: 98;
    margin-left: -75px;
}
.comment_wrapper {
    flex: 25%;
    padding: 10px;
    box-sizing: border-box;
    overflow-y: scroll;
}
.comment_wrapper .title {
    margin-bottom: 10px;
    color: #333;
    font-size: 16px;
}
.comment_list dl {
    position: relative;
    margin-bottom: 15px;
}
.comment_list dl dt {
    position: absolute;
    left: 0;
    top: 3px;
    width: 35px;
    height: 35px;
    overflow: hidden;
    border-radius: 50%;
}
.comment_list dl dt img {
    width: 100%;
    height: 100%;
}
.comment_list dl dd {
    margin-left: 45px;
    color: #333;
    font-size: 12px;
}
.comment_list dl dd:nth-of-type(1) {
    margin-bottom: 5px;
    font-size: 14px;
    font-weight: 700;
}
.audio_con {
    height: 50px;
    background-color: #f1f3f4;
}
.audio_con .myaudio {
    width: 800px;
    height: 40px;
    margin-top: 5px;
    outline: none;
    background-color: #f1f3f4;
}
@keyframes circle {
    0% {
        transform: rotate(0deg);
    }
    100% {
        transform: rotate(360deg);
    }
}
.autoRotate {
    animation-name: circle;
    animation-duration: 10s;
    animation-timing-function: linear;
    animation-delay: 1s;
    animation-iteration-count: infinite;
    animation-play-state: paused;
}
.playing {
    animation-play-state: running;
}
.video_con {
    position: fixed;
    left: 0;
    top: 0;
    right: 0;
    bottom: 0;
    z-index: 99999;
}
.video_con video {
    position: absolute;
    left: 50%;
    top: 50%;
    width: 800px;
    height: 544px;
    transform: translate(-50%, -50%);
}
.video_con .mask {
    width: 100%;
    height: 100%;
    background: url("../images/bg.jpg");
}
```

```js
window.addEventListener("load", function () {
    var app = new Vue({
        el: "#player",
        data: {
            query: "",
            musicList: [],
            musicUrl: "",
            picUrl: "",
            hotComments: [],
            isPlaying: false,
            mvUrl: "",
            isShow: false
        },
        methods: {
            // 歌曲搜索
            searchMusic: function () {
                var that = this;
                axios.get("https://autumnfish.cn/search?keywords=" + this.query)
                    .then(function (response) {
                        that.musicList = response.data.result.songs;
                    })
                    .catch(function (err) {
                        console.log(err);
                    })
            },
            // 播放歌曲
            playMusic: function (musicId) {
                var that = this;
                // 获取歌曲地址
                axios.get("https://autumnfish.cn/song/url?id=" + musicId)
                    .then(function (response) {
                        that.musicUrl = response.data.data[0].url;
                    })
                    .catch(function (err) {
                        console.log(err);
                    });
                // 获取歌曲详细信息
                axios.get("https://autumnfish.cn/song/detail?ids=" + musicId)
                    .then(function (response) {
                        that.picUrl = response.data.songs[0].al.picUrl;
                    })
                    .catch(function (err) {
                        console.log(err);
                    });
                // 歌曲评论获取
                axios.get("https://autumnfish.cn/comment/hot?type=0&id=" + musicId)
                    .then(function (response) {
                        that.hotComments = response.data.hotComments;
                    })
                    .catch(function (err) {
                        console.log(err);
                    })

            },
            // 歌曲播放
            play: function () {
                this.isPlaying = true;
            },
            // 歌曲暂停
            pause: function () {
                this.isPlaying = false;
            },
            // 播放MV
            playMV: function (mvid) {
                var that = this;
                axios.get("https://autumnfish.cn/mv/url?id=" + mvid)
                    .then(function (response) {
                        that.isShow = true;
                        that.mvUrl = response.data.data.url;
                        console.log(that.mvUrl)
                    })
                    .catch(function (err) {
                        console.log(err);
                    })
            },
            // 隐藏MV
            hide: function () {
                this.isShow = false;
            }

        }
    })
});
```

