## 常见问题

```js
function foo(a, b, a) {
    console.log("which a is it?", a);
}
```

```js
var foo = {
    bar: "baz",
    bar: "qux"
};
```

```
var foo = {
    bar: "baz",
    qux: "quux",
};
```

```
if (!a in b) {
    // do something
}
```

```
typeof foo === "strnig"
typeof foo == "undefimed"
typeof bar != "nunber"
typeof bar !== "fucntion"
```

```
var object1 = {
    "foo": "bar",
    "baz": 42,
    "qux-a": true
};
```

```
var object2 = {
    'foo': "bar",
    'baz': 42,
    'qux-a': true
};
```

```
var object3 = {
    foo: "bar",
    baz: 42,
    "qux-a": true
};
```


```
if (foo) {
  bar();
}
else {
  baz();
}
```

```
if (foo) {
  bar();
} else {
  baz();
}
```

```
if (foo) 
{
  bar();
} 
else 
{
  baz();
}

```


```
var obj = {
    a: value,
    bcde:  42,
    fg :   foo()
};
```

```
var obj = {
    a   : value,
    bcde: 42,
    fg  : foo()
};
```

```
var obj = {
    a    :value,
    bcde :42,
    fg   :foo()
};
```

```
var obj = {
    a    : value,
    bcde : 42,
    fg   : foo()
};
```


```
var foo = 5;
var bar = 3;

```

```
var foo = 5;


var bar = 3;

```

```
var foo = 5;





var bar = 3;

```


```
function foo() {
    var bar;
    var baz;
    let qux;
    let norf;
}
```

```
function foo() {
    var bar,
        baz;
    let qux,
        norf;
}
```


```
function withoutSpace(x) {
    // ...
}

function withSpace (x) {
    // ...
}
```

```
foo --;

foo--;
```


# js代码检测

* 保持风格一致
* 提高可读性
* 减少潜在的错误
* 最佳实践


# ESLint

![Nicholas](http://v.eslint.cn/img/nzakas.png)
### [Nicholas C. Zakas](https://github.com/nzakas)


# 今天聊一聊

* eslint 是什么
* eslint 安装&配置
* eslint 集成
* eslint 规则&插件
* eslint 中文
* eslint 架构
* eslint 自动修复
* eslint 存在的问题
* 为什么选择 eslint
* eslint 未来

## ESLint 是什么

The pluggable linting utility for JavaScript and JSX

在这里你只需知道 ESLint 可以进行代码检测即可。稍后再看pluggable
## 安装和配置

```bash
$ node install -g eslint

```

创建配置文件 **.eslintrc.***

```bash
$ eslint --init

```


```js
{
    "env": {
        "browser": true,
        "node": true
    },
    "globals": {
        "VUE": true,
        "__inline": false
    },
    "parserOptions": {
        "ecmaFeatures": {
            "jsx": true
        }
    },
    "plugins": [
        "plugin1",
        "eslint-plugin-plugin2"
    ],
    "rules": {
        "strict": "off",
        "no-loop-func": "warn",
        "semi": "error"
    }
}
```

**注意:** "error"错误，"warn"警告，"off"关闭


## .eslintrc.* 优先级

1. **.eslintrc.js**
2. **.eslintrc.yaml**
3. **.eslintrc.yml**
4. **.eslintrc.json**
5. **~~.eslintrc~~**
6. **package.json**

## [eslint config for sm](https://github.com/smocean/eslint-config-sm)

```bash
$ node install -g eslint-config-sm 
```

配置文件 **.eslintrc.***

```json
{
   "extends": "sm"
}
```

node环境：
```json
{
    "extends": "sm/node-config"
}
```


那么现在再回顾一下 ESLint 描述中的 pluggable，有没有真正体会到！

## 配置层叠和继承

```js
app
├── .eslintrc
├── lib
│ └── source.js
└─┬ tests
  ├── .eslintrc
  └── test.js
```


# [集成](http://eslint.cn/docs/user-guide/integrations)

* [cmd](http://eslint.cn/docs/user-guide/integrations#command-line-tools)
* [Sublime Text 3](https://github.com/roadhump/SublimeLinter-eslint)
* [Vim](https://github.com/scrooloose/syntastic/tree/master/syntax_checkers/javascript)
* IntelliJ IDEA, WebStorm
* Visual Studio Code
* ...


## cmd: [eslint-nibble](https://github.com/IanVS/eslint-nibble)

![http://v.eslint.cn/img/eslint-cmd.png](http://v.eslint.cn/img/eslint-cmd.png)
![http://v.eslint.cn/img/eslint-nibble.png](http://v.eslint.cn/img/eslint-nibble.png)

## [Sublime Text 3](https://github.com/smocean/eslint-config-sm)


![http://v.eslint.cn/img/sublime.png](http://v.eslint.cn/img/sublime.png)

## ESLint中文

* [http://eslint.cn](http://eslint.cn)
* [http://cn.eslint.org](http://cn.eslint.org)
* [http://weibo.com/eslint](http://weibo.com/eslint)
* <span class="green">QQ: 523034328</span>


### 贡献者

* [@coocon](https://github.com/coocon)
* [@cssmagic](https://github.com/cssmagic)
* [@DavidDong93](https://github.com/DavidDong93)
* [@fengnana](https://github.com/fengnana)
* [@freeyiyi1993](https://github.com/freeyiyi1993)
* [@ILFront-End](https://github.com/ILFront-End)
* [@hacke2](https://github.com/hacke2)
* [@maomaoking](https://github.com/maomaoking)
* [@maoshuyu](https://github.com/maoshuyu)
* [@molee1905](http://github.com/molee1905)
* [@qifeigit](https://github.com/qifeigit)
* [@summart](https://github.com/summart)
* [@sunshiner](https://github.com/sunshiner)
* [@wqllpw](https://github.com/wqllpw)
* [@xkf521](https://github.com/xkf521)
* [@yanggao40](https://github.com/yanggao40)
* [@ybbjegj](https://github.com/ybbjegj)


# 高阶


## 架构


![http://v.eslint.cn/img/architecture.png](http://v.eslint.cn/img/architecture.png)


## 自动修复

![http://v.eslint.cn/img/message.png](http://v.eslint.cn/img/message.png)
![http://v.eslint.cn/img/fix.png](http://v.eslint.cn/img/fix.png)


### 可修复的规则


* [no-extra-semi](http://eslint.cn/docs/rules/no-extra-semi)
* [no-multi-spaces](http://eslint.cn/docs/rules/no-multi-spaces)
* [array-bracket-spacing](http://eslint.cn/docs/rules/array-bracket-spacing)
* [block-spacing](http://eslint.cn/docs/rules/block-spacing)
* [comma-spacing](http://eslint.cn/docs/rules/comma-spacing)
* [computed-property-spacing](http://eslint.cn/docs/rules/computed-property-spacing)
* [eol-last](http://eslint.cn/docs/rules/eol-last)
* [jsx-quotes](http://eslint.cn/docs/rules/jsx-quotes)
* [indent](http://eslint.cn/docs/rules/indent)
* [keyword-spacing](http://eslint.cn/docs/rules/keyword-spacing)
* [linebreak-style](http://eslint.cn/docs/rules/linebreak-style)
* [no-spaced-func](http://eslint.cn/docs/rules/no-spaced-func)
* [no-trailing-spaces](http://eslint.cn/docs/rules/no-trailing-spaces)
* [object-curly-spacing](http://eslint.cn/docs/rules/object-curly-spacing)
* [quotes](http://eslint.cn/docs/rules/quotes)
* [semi](http://eslint.cn/docs/rules/semi)
* [space-before-blocks](http://eslint.cn/docs/rules/space-before-blocks)
* [space-before-function-paren](http://eslint.cn/docs/rules/space-before-function-paren)
* [space-in-parens](http://eslint.cn/docs/rules/space-in-parens)
* [space-infix-ops](http://eslint.cn/docs/rules/space-infix-ops)
* [space-unary-ops](http://eslint.cn/docs/rules/space-unary-ops)
* [spaced-comment](http://eslint.cn/docs/rules/spaced-comment)
* [constructor-super](http://eslint.cn/docs/rules/constructor-super)
* [template-curly-spacing](http://eslint.cn/docs/rules/template-curly-spacing)
* [yield-star-spacing](http://eslint.cn/docs/rules/yield-star-spacing)


## 规则 & 插件
 
```bash
$ npm install -g yo

$ npm i -g generator-eslint

```

创建插件:
```bash
$ yo eslint:plugin

```

创建规则:
```bash
$ yo eslint:rule

```

**练练手呗**

## AST

* [estree](https://github.com/estree/estree/blob/master/spec.md)
* [esprima](https://github.com/jquery/esprima/blob/master/src/syntax.ts)
* [acorn](https://github.com/ternjs/acorn)
* [expree](https://github.com/eslint/espree)

## 自动修复存在的问题

我们来看一下自动修复的源码：

```js
// sort in reverse order of occurrence
fixes.sort(function(a, b) {
    if (a.fix.range[1] <= b.fix.range[0]) {
        return 1;
    } else {
        return -1;
    }
});

// split into array of characters for easier manipulation
var chars = text.split("");

fixes.forEach(function(problem) {
    var fix = problem.fix;

    if (fix.range[1] < lastFixPos) {
        chars.splice(fix.range[0], fix.range[1] - fix.range[0], fix.text);
        lastFixPos = fix.range[0];
    } else {
        remainingMessages.push(problem);
    }
});
```

```js
var fixes = [
    {range: [10, 10]},
    {range: [11, 15]},
    {range: [11, 16]}
];
```
降序排列：
```js
var fixes = [
    {range: [11, 15]},
    {range: [11, 16]},
    {range: [10, 10]}
];
```

1. 不能保证所有的修复都被应用到。
2. 可能与其它规则冲突。例如，一个规则能插入逗号，然而另一个规则要求逗号后面有空格。要求有空格的规则并不知道一个新的逗号被加了进来，因为在规则执行后它就结束了。
3. 可能改变作用域的评估。例如，将函数或语句块内的 var 改为 const。可能导致整个规则无效，因为在遍历前，作用域的计算已经结束。
4. 一个修复如果改变了代码的含义，很有可能导致程序出错。

作者自我反思整个项目的设计决策：

1. 自动修复模式应该只进行修复，无需关心不可修复的规则。但是现在，它既扮演者 lint 的角色，也会输出消息。这似乎是不必要的。
2. 目前的修复是基于文本的修复，对于自动修复太过天真。很明显，基于文本的修复可伸缩性很差。
3. 试图将自动修复融入到单一遍历系统的检测过程中，显得力不从心。

## ESLint 3.0

目前可查看multipass分支

![http://v.eslint.cn/img/fix-more-gt-slower.png](http://v.eslint.cn/img/fix-more-gt-slower.png)


## 为什么选择 eslint

* 慕[名](https://github.com/nzakas)而来
* 规则数量丰富 (200+)
* 自由定制
* 支持扩展
* 4月14号 [jscs](https://github.com/jscs-dev/node-jscs)[加入](http://eslint.org/blog/2016/04/welcoming-jscs-to-eslint) eslint

![http://v.eslint.cn/img/do-u-use-eslint.png](http://v.eslint.cn/img/do-u-use-eslint.png)

## eslint 未来

[ESLint 加入了 jQuery 基金会](http://eslint.org/blog/2016/04/eslint-joins-the-jquery-foundation)

在文中，作者说到：一个开源项目达到一定的普及程度之后，维护者就有责任确保它有持续良好的社区，以生存发展下去。在过去几年，一些很重要的项目都出现了问题：YUI不再进行维护，Node.js分裂，Express也变得杂乱无序。社区变得混乱不堪，无所附依。于是就加入了jQuery 基金会，避免 ESLint 重蹈覆辙。jQuery 基金会 门下有很多伟大的项目，比如 jQuery 和 Esprima，在和 Dojo 基金会合并之后，也囊括了Lodash 和 Grunt 等。作者谦虚地说道，能与这些重要而且有影响力的项目为伍，感到自豪。

那么加入[jQuery 基金会](https://jquery.org/mission/)，可以确保以下几个事情：

1. 项目不会因为作者本人离开而停止。虽然作者并没计划离开，但，纵观历史，开源项目的创始人最终离开自己的项目甚是常见。从John Resig 离开 jQuery 到 Ryan Dahl 离开 Node.js，作者无法想象自己也会走他们走过的路。
2. ESLint 将永远不会卖给某个公司。从  Node.js 和 Express 事件看来，这种关系并不总是一帆风顺。ESLint 社区应该得到承诺，依赖 ESLint 是安全的，是没有问题的。
3. ESLint 项目将继续跟进与开源有关的最新的最佳实践和合法建议。




