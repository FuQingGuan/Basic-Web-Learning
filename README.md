# Web 学习

## 前端技术栈类比

![](https://oss.yiki.tech/img/202305182122951.png)

## 常用插件

| 插件名称                                                     |
| ------------------------------------------------------------ |
| Auto Close Tag                                               |
| Auto Rename Tag                                              |
| ESLint                                                       |
| HTML CSS Support                                             |
| HTML Snippets                                                |
| JavaScript (ES6) code snippets                               |
| Live Server                                                  |
| open in browser                                              |
| Vetur                                                        |
| Chinese (Simplified) (简体中文) Language Pack for Visual Studio Code |

## 快捷键

> ⇧ + ! 快速生成 html 文档

![](https://oss.yiki.tech/img/202305182245789.png)

![](https://oss.yiki.tech/img/202305182245214.png)

## ES 6

> `ECMAScript 6.0`（以下简称 ES6）`是 JavaScript 语言的下一代标准`，已经在 2015 年 6 月正式发布了。它的目标，是使得 JavaScript 语言可以用来编写复杂的大型应用程序，成为企业级开发语言。`每年一个新版本`

### Let

* let 声明的变量有严格局部作用域

```html
    <script>
        {
            // var 声明的变量往往会越域
            var a = 1;
            // let 声明的变量有严格局部作用域
            let b = 2;
        }
        console.log(a); // 1
        console.log(b); // b is not defined，b 未定义
    </script>
```

![](https://oss.yiki.tech/img/202305182253002.png)

* let 只能声明一次

```html
    <script>
        // var 可以声明多次
        // let 只能声明一次
        var m = 1;
        var m = 2;
        let n = 3;
        // 报错
        len n = 4; // 意外的标识符 'n'
        console.log(m);
        console.log(n);
    </script>
```

![](https://oss.yiki.tech/img/202305182257011.png)

* let 不存在变量提升

> 变量提升（Variable Hoisting）是JavaScript中的一个特性，它指的是在代码执行之前，变量声明会被提升到其所在作用域的顶部。这意味着无论变量声明在作用域的哪个位置，都会被视为在作用域的顶部进行处理。
> 
> 使用var关键字声明的变量x会被提升，但是其赋值操作不会被提升。因此，第一个console.log(x)语句输出undefined，表示x变量已经声明，但尚未赋值。 
> 而使用let关键字声明的变量y不会被提升，因此第二个console.log(y)语句会抛出ReferenceError，表示在变量初始化之前无法访问y，因为let变量不会在声明之前进入作用域。

```html
    <script>
        // var 会变量提升
        // let 不存在变量提升
        console.log(x); // undefined
        var x = 10;
        console.log(y); // ReferenceError: Cannot access 'y' before initialization, 初始化前无法访问“y”
        let y = 20;
    </script>
```

![](https://oss.yiki.tech/img/202305182302721.png)

### const 声明常量(只读变量)

```html
    <script>
        /**
         * 1. 声明之后不允许改变
         * 2. 一但声明必须初始化, 否则会报错
         */
        const a = 1;
        a = 3;
    </script>
```

![](https://oss.yiki.tech/img/202305182306738.png)

### 解构表达式

#### 数组解构

```html
    <script>
        let arr = [1, 2, 3];

        let a = arr[0];
        let b = arr[1];
        let c = arr[2];

        console.log(a, b, c);
    </script>
```

![](https://oss.yiki.tech/img/202305192208910.png)

```html
    <script>
        let arr = [1, 2, 3];

        // let a = arr[0];
        // let b = arr[1];
        // let c = arr[2];
        
        let [a, b, c] = arr;

        console.log(a, b, c);
    </script>
```

![](https://oss.yiki.tech/img/202305192210379.png)

#### 对象解构

```html
    <script>
        const person = {
            name: "jack",
            age: 21,
            language: ['java', 'js', 'css']
        }

        const name = person.name;
        const age = person.age;
        const language = person.language;

        console.log(name, age, language);

    </script>
```

![](https://oss.yiki.tech/img/202305192214261.png)

```html
    <script>
        const person = {
            name: "jack",
            age: 21,
            language: ['java', 'js', 'css']
        }

        // const name = person.name;
        // const age = person.age;
        // const language = person.language;

        // 对象解构
        const {name, age, language} = person;

        console.log(name, age, language);

    </script>
```

![](https://oss.yiki.tech/img/202305192216509.png)

```html
    <script>
        const person = {
            name: "jack",
            age: 21,
            language: ['java', 'js', 'css']
        }

        // const name = person.name;
        // const age = person.age;
        // const language = person.language;

        // 对象解构
        const {name:abc, age, language} = person;

        console.log(abc, age, language);

    </script>
```

![](https://oss.yiki.tech/img/202305192216909.png)

### 字符串扩展

#### 新 API

```html
    <script>
        let str = "hello.vue";
        // 是否以 hello 开始
        console.log(str.startsWith("hello")); // true
        // 是否以 .vue 结束
        console.log(str.endsWith(".vue")); // true
        // 是否包含
        console.log(str.includes("e")); // true
        console.log(str.includes("hello")); // true
    </script>
```

![](https://oss.yiki.tech/img/202305192222231.png)

#### 字符串模版

```html
    <script>
        // 字符串模版
        let str = 
        `
            <div>
                <span>hello world</span>
            </div>
        `

        console.log(str);
    </script>
```

![](https://oss.yiki.tech/img/202305192333893.png)

```html
    <script>
        // 字符串插入变量和表达式。变量名写在 ${} 中，${} 中可以放入 JavaScript 表达式
        let name = "张三";
        let age = 24;
        let info = `我是 ${name}, 今年 ${age} 了`

        console.log(info);
    </script>
```

![](https://oss.yiki.tech/img/202305192337492.png)

```html
    <script>
        // 字符串插入变量和表达式。变量名写在 ${} 中，${} 中可以放入 JavaScript 表达式
        let name = "张三";
        let age = 24;
        let info = `我是 ${name}, 今年 ${age + 10} 了`

        console.log(info);
    </script>
```

![](https://oss.yiki.tech/img/202305192338687.png)

```html
    <script>
        // 字符串插入变量和表达式。变量名写在 ${} 中，${} 中可以放入 JavaScript 表达式
        function fun() {
            return "这是一个函数";
        }

        let name = "张三";
        let age = 24;
        let info = `我是 ${name}, 今年 ${age + 10} 了。我想说：${fun()}`

        console.log(info);
    </script>
```

![](https://oss.yiki.tech/img/202305192344732.png)

### 函数优化

#### 函数参数默认值

```html
    <script>
        // 在 ES6 以前, 我们无法给一个函数参数设置默认值, 只能采用变通写法
        function add(a, b) {
            // 判断 b 是否为空，为空就给默认值 1
            b = b || 1;
            
            return a + b;
        }

        // 传递一个参数
        console.log(add(10));
    </script>
```

![](https://oss.yiki.tech/img/202305192348281.png)

```html
    <script>
        // ES 6 及以后可以直接给参数写上默认值，没传递就回自动使用默认值
        function add2(a, b = 1) {
            return a + b;
        }

        console.log(add2(20));
    </script>
```

![](https://oss.yiki.tech/img/202305192351088.png)

#### 不定参数

```html
    <script>
        // 在 ES6 以前, 我们无法给一个函数参数设置默认值, 只能采用变通写法
        function fun(...values) {
            console.log(values.length);
        }

        fun(1, 2); // 2
        fun(1, 2, 3) // 3
    </script>
```

![](https://oss.yiki.tech/img/202305200024890.png)

#### 箭头函数

```html
    <script>
        var print = obj => console.log(obj);
        print("hello");
    </script>
```

![](https://oss.yiki.tech/img/202305200025130.png)
