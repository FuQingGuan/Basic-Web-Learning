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
