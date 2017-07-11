# myeslint-rules
构建eslint需知
# 开始使用
- npm i -g eslint
- eslint --init (选择大概的eslint样式)
- 按照自己项目使用的框架情况使用
- 每个规则有三个等级:off ,warn, error (0,1,2)
  off表示禁用这条规则，warn表示仅给出警告，并不会导致检查不通过，而error则会导致检查不通过。
# 配置
``` 
module.exports = {
  "env": {
    "browser": true,
    "commonjs": true,
    "es6": true
  },
  "settings": {
    "react": {
      "pragma": "React"
    }
  },
  "extends": "eslint:recommended",
  "parserOptions": {
    "ecmaFeatures": {
      "experimentalObjectRestSpread": true,
      "jsx": true
    },
    "ecmaVersion": 6,
    "sourceType": "module",
    "ecmaFeatures": {
      "jsx": true
    },
    "sourceType": "module"
  },
  "plugins": [
    "react"
  ],
  "rules": {
    "react/jsx-uses-react": 1,
    "react/jsx-uses-vars": 1,
    "brace-style": [2, "1tbs", {
module.exports = {
	// Environment可以预设好的其他环境的全局变量，如brower、node环境变量、es6环境变量、mocha环境变量等
  "env": {
    "browser": true,
    "commonjs": true,
    "es6": true
  },
  "settings": {
    "react": {
      "pragma": "React"
    }
  },
  "extends": "eslint:recommended",
  "parserOptions": { // 允许支持的es的版本.以及一些特性
    "ecmaFeatures": {
      "experimentalObjectRestSpread": true,
      "jsx": true
    },
    "ecmaVersion": 6,
    "sourceType": "module", //指定来源的类型，有两种”script”或”module”
    "ecmaFeatures": {
      "jsx": true // 启动JSX
    },
  },
	// 允许使用插件
  "plugins": [
    "react"
  ],
  "rules": {
    "react/jsx-uses-react": 1,
    "react/jsx-uses-vars": 1,
    "brace-style": [2, "1tbs", {
      "allowSingleLine": true
    }],
    "camelcase": 2, // 驼峰命名
    'no-console': 'off', // console.log 不会报错
    "semi-spacing": ["error", { // 分号前后添加空格
      "before": false,
      "after": true
    }],
    "comma-dangle": 2, // 逗号报错
    "quotes": [2, "single"], // 单引号必须为单引号
    "no-undef": 1,
    "global-strict": 0,
    "no-extra-semi": 2, // 禁用没必要的分号
    "no-underscore-dangle": 0, // 禁止标识符中有悬空下划线
    "no-console": 0, // console.log 不报错
    "no-unused-vars": 2, // 声明了不使用
    "brace-style": [2, "1tbs", { // 大括号风格要求,1tbs就是我平时使用if else风格
      "allowSingleLine": true
    }],
    "no-trailing-spaces": [1, { // 禁用行尾空白
      "skipBlankLines": true
    }],
    "no-unreachable": 1,
    "no-alert": 0,
    "react/jsx-uses-react": 1,
    "react/jsx-uses-vars": 1,
    "indent": ["error", 2],
    "linebreak-style": [
      "error",
      "unix"
    ],
    "semi": [
      "error",
      "always"
    ],
  }
};
```
# 摘录的配置详情
```
1 "no-alert": 0,//禁止使用alert confirm prompt
  2 "no-array-constructor": 2,//禁止使用数组构造器
  3 "no-bitwise": 0,//禁止使用按位运算符
  4 "no-caller": 1,//禁止使用arguments.caller或arguments.callee
  5 "no-catch-shadow": 2,//禁止catch子句参数与外部作用域变量同名
  6 "no-class-assign": 2,//禁止给类赋值
  7 "no-cond-assign": 2,//禁止在条件表达式中使用赋值语句
  8 "no-console": 2,//禁止使用console
  9 "no-const-assign": 2,//禁止修改const声明的变量
 10 "no-constant-condition": 2,//禁止在条件中使用常量表达式 if(true) if(1)
 11 "no-continue": 0,//禁止使用continue
 12 "no-control-regex": 2,//禁止在正则表达式中使用控制字符
 13 "no-debugger": 2,//禁止使用debugger
 14 "no-delete-var": 2,//不能对var声明的变量使用delete操作符
 15 "no-div-regex": 1,//不能使用看起来像除法的正则表达式/=foo/
 16 "no-dupe-keys": 2,//在创建对象字面量时不允许键重复 {a:1,a:1}
 17 "no-dupe-args": 2,//函数参数不能重复
 18 "no-duplicate-case": 2,//switch中的case标签不能重复
 19 "no-else-return": 2,//如果if语句里面有return,后面不能跟else语句
 20 "no-empty": 2,//块语句中的内容不能为空
 21 "no-empty-character-class": 2,//正则表达式中的[]内容不能为空
 22 "no-empty-label": 2,//禁止使用空label
 23 "no-eq-null": 2,//禁止对null使用==或!=运算符
 24 "no-eval": 1,//禁止使用eval
 25 "no-ex-assign": 2,//禁止给catch语句中的异常参数赋值
 26 "no-extend-native": 2,//禁止扩展native对象
 27 "no-extra-bind": 2,//禁止不必要的函数绑定
 28 "no-extra-boolean-cast": 2,//禁止不必要的bool转换
 29 "no-extra-parens": 2,//禁止非必要的括号
 30 "no-extra-semi": 2,//禁止多余的冒号
 31 "no-fallthrough": 1,//禁止switch穿透
 32 "no-floating-decimal": 2,//禁止省略浮点数中的0 .5 3.
 33 "no-func-assign": 2,//禁止重复的函数声明
 34 "no-implicit-coercion": 1,//禁止隐式转换
 35 "no-implied-eval": 2,//禁止使用隐式eval
 36 "no-inline-comments": 0,//禁止行内备注
 37 "no-inner-declarations": [2, "functions"],//禁止在块语句中使用声明（变量或函数）
 38 "no-invalid-regexp": 2,//禁止无效的正则表达式
 39 "no-invalid-this": 2,//禁止无效的this，只能用在构造器，类，对象字面量
 40 "no-irregular-whitespace": 2,//不能有不规则的空格
 41 "no-iterator": 2,//禁止使用__iterator__ 属性
 42 "no-label-var": 2,//label名不能与var声明的变量名相同
 43 "no-labels": 2,//禁止标签声明
 44 "no-lone-blocks": 2,//禁止不必要的嵌套块
 45 "no-lonely-if": 2,//禁止else语句内只有if语句
 46 "no-loop-func": 1,//禁止在循环中使用函数（如果没有引用外部变量不形成闭包就可以）
 47 "no-mixed-requires": [0, false],//声明时不能混用声明类型
 48 "no-mixed-spaces-and-tabs": [2, false],//禁止混用tab和空格
 49 "linebreak-style": [0, "windows"],//换行风格
 50 "no-multi-spaces": 1,//不能用多余的空格
 51 "no-multi-str": 2,//字符串不能用\换行
 52 "no-multiple-empty-lines": [1, {"max": 2}],//空行最多不能超过2行
 53 "no-native-reassign": 2,//不能重写native对象
 54 "no-negated-in-lhs": 2,//in 操作符的左边不能有!
 55 "no-nested-ternary": 0,//禁止使用嵌套的三目运算
 56 "no-new": 1,//禁止在使用new构造一个实例后不赋值
 57 "no-new-func": 1,//禁止使用new Function
 58 "no-new-object": 2,//禁止使用new Object()
 59 "no-new-require": 2,//禁止使用new require
 60 "no-new-wrappers": 2,//禁止使用new创建包装实例，new String new Boolean new Number
 61 "no-obj-calls": 2,//不能调用内置的全局对象，比如Math() JSON()
 62 "no-octal": 2,//禁止使用八进制数字
 63 "no-octal-escape": 2,//禁止使用八进制转义序列
 64 "no-param-reassign": 2,//禁止给参数重新赋值
 65 "no-path-concat": 0,//node中不能使用__dirname或__filename做路径拼接
 66 "no-plusplus": 0,//禁止使用++，--
 67 "no-process-env": 0,//禁止使用process.env
 68 "no-process-exit": 0,//禁止使用process.exit()
 69 "no-proto": 2,//禁止使用__proto__属性
 70 "no-redeclare": 2,//禁止重复声明变量
 71 "no-regex-spaces": 2,//禁止在正则表达式字面量中使用多个空格 /foo bar/
 72 "no-restricted-modules": 0,//如果禁用了指定模块，使用就会报错
 73 "no-return-assign": 1,//return 语句中不能有赋值表达式
 74 "no-script-url": 0,//禁止使用javascript:void(0)
 75 "no-self-compare": 2,//不能比较自身
 76 "no-sequences": 0,//禁止使用逗号运算符
 77 "no-shadow": 2,//外部作用域中的变量不能与它所包含的作用域中的变量或参数同名
 78 "no-shadow-restricted-names": 2,//严格模式中规定的限制标识符不能作为声明时的变量名使用
 79 "no-spaced-func": 2,//函数调用时 函数名与()之间不能有空格
 80 "no-sparse-arrays": 2,//禁止稀疏数组， [1,,2]
 81 "no-sync": 0,//nodejs 禁止同步方法
 82 "no-ternary": 0,//禁止使用三目运算符
 83 "no-trailing-spaces": 1,//一行结束后面不要有空格
 84 "no-this-before-super": 0,//在调用super()之前不能使用this或super
 85 "no-throw-literal": 2,//禁止抛出字面量错误 throw "error";
 86 "no-undef": 1,//不能有未定义的变量
 87 "no-undef-init": 2,//变量初始化时不能直接给它赋值为undefined
 88 "no-undefined": 2,//不能使用undefined
 89 "no-unexpected-multiline": 2,//避免多行表达式
 90 "no-underscore-dangle": 1,//标识符不能以_开头或结尾
 91 "no-unneeded-ternary": 2,//禁止不必要的嵌套 var isYes = answer === 1 ? true : false;
 92 "no-unreachable": 2,//不能有无法执行的代码
 93 "no-unused-expressions": 2,//禁止无用的表达式
 94 "no-unused-vars": [2, {"vars": "all", "args": "after-used"}],//不能有声明后未被使用的变量或参数
 95 "no-use-before-define": 2,//未定义前不能使用
 96 "no-useless-call": 2,//禁止不必要的call和apply
 97 "no-void": 2,//禁用void操作符
 98 "no-var": 0,//禁用var，用let和const代替
 99 "no-warning-comments": [1, { "terms": ["todo", "fixme", "xxx"], "location": "start" }],//不能有警告备注
100 "no-with": 2,//禁用with
101 
102 "array-bracket-spacing": [2, "never"],//是否允许非空数组里面有多余的空格
103 "arrow-parens": 0,//箭头函数用小括号括起来
104 "arrow-spacing": 0,//=>的前/后括号
105 "accessor-pairs": 0,//在对象中使用getter/setter
106 "block-scoped-var": 0,//块语句中使用var
107 "brace-style": [1, "1tbs"],//大括号风格
108 "callback-return": 1,//避免多次调用回调什么的
109 "camelcase": 2,//强制驼峰法命名
110 "comma-dangle": [2, "never"],//对象字面量项尾不能有逗号
111 "comma-spacing": 0,//逗号前后的空格
112 "comma-style": [2, "last"],//逗号风格，换行时在行首还是行尾
113 "complexity": [0, 11],//循环复杂度
114 "computed-property-spacing": [0, "never"],//是否允许计算后的键名什么的
115 "consistent-return": 0,//return 后面是否允许省略
116 "consistent-this": [2, "that"],//this别名
117 "constructor-super": 0,//非派生类不能调用super，派生类必须调用super
118 "curly": [2, "all"],//必须使用 if(){} 中的{}
119 "default-case": 2,//switch语句最后必须有default
120 "dot-location": 0,//对象访问符的位置，换行的时候在行首还是行尾
121 "dot-notation": [0, { "allowKeywords": true }],//避免不必要的方括号
122 "eol-last": 0,//文件以单一的换行符结束
123 "eqeqeq": 2,//必须使用全等
124 "func-names": 0,//函数表达式必须有名字
125 "func-style": [0, "declaration"],//函数风格，规定只能使用函数声明/函数表达式
126 "generator-star-spacing": 0,//生成器函数*的前后空格
127 "guard-for-in": 0,//for in循环要用if语句过滤
128 "handle-callback-err": 0,//nodejs 处理错误
129 "id-length": 0,//变量名长度
130 "indent": [2, 4],//缩进风格
131 "init-declarations": 0,//声明时必须赋初值
132 "key-spacing": [0, { "beforeColon": false, "afterColon": true }],//对象字面量中冒号的前后空格
133 "lines-around-comment": 0,//行前/行后备注
134 "max-depth": [0, 4],//嵌套块深度
135 "max-len": [0, 80, 4],//字符串最大长度
136 "max-nested-callbacks": [0, 2],//回调嵌套深度
137 "max-params": [0, 3],//函数最多只能有3个参数
138 "max-statements": [0, 10],//函数内最多有几个声明
139 "new-cap": 2,//函数名首行大写必须使用new方式调用，首行小写必须用不带new方式调用
140 "new-parens": 2,//new时必须加小括号
141 "newline-after-var": 2,//变量声明后是否需要空一行
142 "object-curly-spacing": [0, "never"],//大括号内是否允许不必要的空格
143 "object-shorthand": 0,//强制对象字面量缩写语法
144 "one-var": 1,//连续声明
145 "operator-assignment": [0, "always"],//赋值运算符 += -=什么的
146 "operator-linebreak": [2, "after"],//换行时运算符在行尾还是行首
147 "padded-blocks": 0,//块语句内行首行尾是否要空行
148 "prefer-const": 0,//首选const
149 "prefer-spread": 0,//首选展开运算
150 "prefer-reflect": 0,//首选Reflect的方法
151 "quotes": [1, "single"],//引号类型 `` "" ''
152 "quote-props":[2, "always"],//对象字面量中的属性名是否强制双引号
153 "radix": 2,//parseInt必须指定第二个参数
154 "id-match": 0,//命名检测
155 "require-yield": 0,//生成器函数必须有yield
156 "semi": [2, "always"],//语句强制分号结尾
157 "semi-spacing": [0, {"before": false, "after": true}],//分号前后空格
158 "sort-vars": 0,//变量声明时排序
159 "space-after-keywords": [0, "always"],//关键字后面是否要空一格
160 "space-before-blocks": [0, "always"],//不以新行开始的块{前面要不要有空格
161 "space-before-function-paren": [0, "always"],//函数定义时括号前面要不要有空格
162 "space-in-parens": [0, "never"],//小括号里面要不要有空格
163 "space-infix-ops": 0,//中缀操作符周围要不要有空格
164 "space-return-throw-case": 2,//return throw case后面要不要加空格
165 "space-unary-ops": [0, { "words": true, "nonwords": false }],//一元运算符的前/后要不要加空格
166 "spaced-comment": 0,//注释风格要不要有空格什么的
167 "strict": 2,//使用严格模式
168 "use-isnan": 2,//禁止比较时使用NaN，只能用isNaN()
169 "valid-jsdoc": 0,//jsdoc规则
170 "valid-typeof": 2,//必须使用合法的typeof的值
171 "vars-on-top": 2,//var必须放在作用域顶部
172 "wrap-iife": [2, "inside"],//立即执行函数表达式的小括号风格
173 "wrap-regex": 0,//正则表达式字面量用小括号包起来
174 "yoda": [2, "never"]//禁止尤达条件
```
