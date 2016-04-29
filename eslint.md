title: ESLint In Action
speaker: molee1905
url: https://github.com/ksky521/nodePPT
transition: slide2
files: /css/eslint.css
theme: moon

[slide]

[slide]

总要找些事儿做，都静止了，地球还怎么转

[slide]

于是，很多人选择了敲代码

[slide]

很多人

[slide] 

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

[slide]

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

[slide]

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

[slide]

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

[slide] 

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

[slide]

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

[slide]

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

[slide]

# js代码检测 {:&.flexbox.vleft}

* 保持风格一致
* 提高可读性
* 减少潜在的错误
* 最佳实践

[slide]
# ESLint
---

![Nicholas](http://v.eslint.cn/img/nzakas.png)
### [Nicholas C. Zakas](https://github.com/nzakas)

[slide]
# 今天聊一聊

* eslint 是什么 {:&.rollIn}
* eslint 安装&配置
* eslint 集成
* eslint 规则&插件
* eslint 中文
* eslint 架构
* eslint 自动修复
* eslint 存在的问题
* 为什么选择 eslint
* eslint 未来

[slide]
# ESLint 是什么

The pluggable linting utility for JavaScript and JSX

[slide]
# 安装和配置 {:&.flexbox.vleft}

```bash
$ node install -g eslint

```

创建配置文件 ** .eslintrc.* **

```bash
$ eslint --init

```

[slide]

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

[slide]
# .eslintrc.* 优先级 {:&.flexbox.vleft}

1. ** .eslintrc.js **
2. ** .eslintrc.yaml **
3. ** .eslintrc.yml **
4. ** .eslintrc.json **
5. ** ~~.eslintrc~~ **
6. ** package.json **


[slide]

# eslint config for sm {:&.flexbox.vleft}


```bash
$ node install -g eslint-config-sm 
```


配置文件 **.eslintrc.* **

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

[eslint-config-sm](https://github.com/smocean/eslint-config-sm)

[slide]
# 配置层叠和继承 {:&.flexbox.vleft}

```js
app
├── .eslintrc
├── lib
│ └── source.js
└─┬ tests
  ├── .eslintrc
  └── test.js
```


[slide]
# [集成](http://eslint.cn/docs/user-guide/integrations)

* [cmd](http://eslint.cn/docs/user-guide/integrations#command-line-tools)
* [Sublime Text 3](https://github.com/roadhump/SublimeLinter-eslint)
* [Vim](https://github.com/scrooloose/syntastic/tree/master/syntax_checkers/javascript)
* IntelliJ IDEA, WebStorm
* Visual Studio Code
* ...

[slide]
# cmd: [eslint-nibble](https://github.com/IanVS/eslint-nibble)

![http://v.eslint.cn/img/eslint-cmd.png](http://v.eslint.cn/img/eslint-cmd.png)

[slide]
![http://v.eslint.cn/img/eslint-nibble.png](http://v.eslint.cn/img/eslint-nibble.png)

[slide]
# [Sublime Text 3](https://github.com/smocean/eslint-config-sm)

![http://v.eslint.cn/img/sublime.png](http://v.eslint.cn/img/sublime.png)

[slide]
# ESLint中文 {:&.flexbox.vleft}

* [http://eslint.cn](http://eslint.cn)
* [http://cn.eslint.org](http://cn.eslint.org)
* [http://weibo.com/eslint](http://weibo.com/eslint)
* <span class="green">QQ: 523034328</span>

[slide]
# 贡献者 {:&.flexbox.vleft.contributor}

[@coocon](https://github.com/coocon)
[@cssmagic](https://github.com/cssmagic)
[@DavidDong93](https://github.com/DavidDong93)
[@fengnana](https://github.com/fengnana)
[@freeyiyi1993](https://github.com/freeyiyi1993)
[@ILFront-End](https://github.com/ILFront-End)
[@hacke2](https://github.com/hacke2)
[@maomaoking](https://github.com/maomaoking)
[@maoshuyu](https://github.com/maoshuyu)
[@molee1905](http://github.com/molee1905)
[@qifeigit](https://github.com/qifeigit)
[@summart](https://github.com/summart)
[@sunshiner](https://github.com/sunshiner)
[@wqllpw](https://github.com/wqllpw)
[@xkf521](https://github.com/xkf521)
[@yanggao40](https://github.com/yanggao40)
[@ybbjegj](https://github.com/ybbjegj)

[slide] 
# 高阶

[slide]
# 架构

![http://v.eslint.cn/img/architecture.png](http://v.eslint.cn/img/architecture.png)

[slide]
# 自动修复

<div class="columns2">
    <img src="http://v.eslint.cn/img/message.png" height="450">
    <img src="http://v.eslint.cn/img/fix.png" height="450">
</div>

[slide]
# 可修复的规则 {:&.flexbox.vleft}

[no-extra-semi](http://eslint.cn/docs/rules/no-extra-semi)
[no-multi-spaces](http://eslint.cn/docs/rules/no-multi-spaces)
[array-bracket-spacing](http://eslint.cn/docs/rules/array-bracket-spacing)
[block-spacing](http://eslint.cn/docs/rules/block-spacing)
[comma-spacing](http://eslint.cn/docs/rules/comma-spacing)
[computed-property-spacing](http://eslint.cn/docs/rules/computed-property-spacing)
[eol-last](http://eslint.cn/docs/rules/eol-last)
[jsx-quotes](http://eslint.cn/docs/rules/jsx-quotes)
[indent](http://eslint.cn/docs/rules/indent)
[keyword-spacing](http://eslint.cn/docs/rules/keyword-spacing)
[linebreak-style](http://eslint.cn/docs/rules/linebreak-style)
[no-spaced-func](http://eslint.cn/docs/rules/no-spaced-func)
[no-trailing-spaces](http://eslint.cn/docs/rules/no-trailing-spaces)
[object-curly-spacing](http://eslint.cn/docs/rules/object-curly-spacing)
[quotes](http://eslint.cn/docs/rules/quotes)
[semi](http://eslint.cn/docs/rules/semi)
[space-before-blocks](http://eslint.cn/docs/rules/space-before-blocks)
[space-before-function-paren](http://eslint.cn/docs/rules/space-before-function-paren)
[space-in-parens](http://eslint.cn/docs/rules/space-in-parens)
[space-infix-ops](http://eslint.cn/docs/rules/space-infix-ops)
[space-unary-ops](http://eslint.cn/docs/rules/space-unary-ops)
[spaced-comment](http://eslint.cn/docs/rules/spaced-comment)
[constructor-super](http://eslint.cn/docs/rules/constructor-super)
[template-curly-spacing](http://eslint.cn/docs/rules/template-curly-spacing)
[yield-star-spacing](http://eslint.cn/docs/rules/yield-star-spacing)

[slide] 
# 规则 & 插件 {:&.flexbox.vleft}
 
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

[slide]
# AST {:&.flexbox.vleft}

* [estree](https://github.com/estree/estree/blob/master/spec.md)
* [esprima](https://github.com/jquery/esprima/blob/master/src/syntax.ts)
* [acorn](https://github.com/ternjs/acorn)
* [expree](https://github.com/eslint/espree)

[slide]
# 自动修复存在的问题 {:&.flexbox.vleft}

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

[slide]

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

[slide]

1. 不能保证所有的修复都被应用到。
2. 可能与其它规则冲突。
3. 可能改变作用的评估。
4. 一个修复如果改变了代码的含义，很有可能导致程序出错。

[slide]
## ESLint 3.0

![http://v.eslint.cn/img/fix-more-gt-slower.png](http://v.eslint.cn/img/fix-more-gt-slower.png)

[slide]
# 为什么选择 eslint {:&.flexbox.vleft}

* 慕[名](https://github.com/nzakas)而来
* 规则数量丰富 (200+)
* 自由定制
* 支持扩展
* 4月14号 [jscs](https://github.com/jscs-dev/node-jscs)[加入](http://eslint.org/blog/2016/04/welcoming-jscs-to-eslint) eslint

[slide]

![http://v.eslint.cn/img/do-u-use-eslint.png](http://v.eslint.cn/img/do-u-use-eslint.png)

[slide]
# eslint 未来 {:&.flexbox.vleft}

[ESLint 加入了 jQuery Foundation](http://eslint.org/blog/2016/04/eslint-joins-the-jquery-foundation)


[slide]
# Thanks for your time
