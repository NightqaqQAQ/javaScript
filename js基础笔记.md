# JavaScript 的引用方式
- js有三种引用方式
    - 写在head里面`<script></script>`
    - 写在body最后一行
    - 写在外部 外部引用 link
> 一般都是在body最后一行用外部引用

# JavaScript 的输出方式
- console.log('你好');  在控制台输出你好
- alert('你好');  在网页弹出框弹出你好
- prompt('请输入你的名字');  在网页弹出框弹出让用户输入的窗口
- document.write('你好');  在网页写入你好

# JaveScript 的变量
### 变量的命名
- 用 var声明:
    - var a = '你好';
    - 变量必须先定义(声明),在使用
- 变量名声明规则
    - 变量名 有命名规则
         1. 只能使用 字母,数字,下划线_ $
         2. 严格区分大小写  变量a 和 变量A 不一样
         3. 不能以数字开头 2a 错误
         4. 不能使用js当中的 关键字和保留字 (具有特殊功能的短语)
         5. 驼峰命名 firstName navItem
         6. 语义化  见名知意

### 变量的数据类型
- 字符串类型 String
    - 用引号引起来  引号不能嵌套(单引号里边不能嵌套单引号)
- 数字类型 Number'
    - 直接输入数字
    - NaN表示不是数字  
    - isNaN() 用来判断是不是NaN类型 true false
    - 用tyopeof判断时NaN也是Number类型
- 布尔值Boolean
    - 只有两个值 ture flase 用于逻辑判断    
- undefined
    - 声明了一个变量 但是没有赋值
    - 只有声明变量了 才会是undefined 不然报错
    - 当typeof检索时没有声名对象时会隐性声明一个空对象
- 空对象 null
    - 声明一个变量 给他赋值null 表示空对象
    - 当typeof检索时返回object
- 数组[]
    - 通常来表示同一组数据类型
    - 里面的数据可以是任意类型 用逗号隔开
- 对象{}
    - 对一个东西的描述
    - key: value
    - 用逗号隔开
- 函数
    - 'function'关键字 声明函数(定义) 函数名(函数的参数) {执行的代码}
    ```html
        function say() {
            alert("你好");   这个函数调用时,执行的代码
        }
    ```
    - 函数 不调用  是 不会执行的
        - say(); 调用

### 变量值的传递
- 赋值运算符 =      a=b
    - 将等号右边的值， 赋给左边的变量； 等号右边的变量值不变。

### 变量的数据类型转换
> a为任意基础类型
- 转为字符串 String
    - a+''加一个空字符串或拼接一个字符串 
    - a.toString()对空字符和未付值的变量无效
    - String(a)
- 转为布尔值 Boolean
    - Boolean(a)
        - 0 NaN null 未赋值 空字符串 是flase 其余的是turn
- 转为数字 Number
    - turn 1 
    - flase 0
    - 声明未赋值 NaN
    - null 0
    - 转化字符串时 字符串为纯数字直接转化
        - 有非数字的转为NaN
        - 如果是空的或空格转为0
##### parseInt和parseFloat
- 专门用来把字符串转为数字
    - parseInt从第一位开始截取整数数字 遇到别的符号就结束
    - parseFloat从第一个整数截取到第一个小数点后面的数
    第二个小数点不截
    - console.log(parseInt('ab', 16))可以把ab转为16进制
    - 转化100px时为NaN
### 算术运算符
- 加号    var sum = a + b; // 106
- 减号   var cha = a - b; // 94
- 乘号   var ji = a * b; // 600
- 除号    var shang = a / b; // 16.666666666666668
- 取余  var yu = a % b;  // 3%2 = 1
    - 当加法运算时有任意一方是字符串则把加号当作拼接字符串 必须两个之间 三个中第一个或最后一个是字符串 前后还是相加
    - 任意非数字的运算都会把两方先转换为数字 在进行+ - ...
    - NaN参与的运算结果都是NaN.
### 赋值运算符
- `+=。`a += 5 等价于 a = a + 5

- `-=。`a -= 5 等价于 a = a - 5

- `*=。`a _= 5 等价于 a = a _ 5

- `/=。`a /= 5 等价于 a = a / 5

- `%=。`a %= 5 等价于 a = a % 5

- `a++`的值等于原变量的值（a 自增前的值）

- `++a`的值等于新值 （a 自增后的值）

自减 --   同理
### 比较运算符
- 通过比较运算符可以比较两个值之间的大小关系，如果关系成立它会返回 true，
如果关系不成立则返回 false。
- 对于非数值进行比较时，会将其转换为数字然后再比较
- 如果符号两侧的值都是字符串时，不会将其转换为数字进行比较。
而是转为比较Unicode编码
- 任何值和 NaN 做任何比较都是 false
- ==这个符号并不严谨，会将不同类型的东西，转为相同类型进行比较  !=不等于
- ===绝对等于 会先比较数据类型,在比较数据   !== 不等于
- undefined 衍生自 null，所以这两个值做相等判断时，会返回 true。
- NaN 不和任何值相等，包括他本身。
### Math对象
- Math.abs(-100)  100 求绝对值
- Math.floor(2.6)  2 向下取整
- Math.floor(-2.6)  3
- Math.ceil(2.4) 3 向上取整
- Math.ceil(-2.4) 2 
- Math.round()	四舍五入取整（正数四舍五入，负数五舍六入）
    - console.log(Math.round(2.5)); // 3
    - console.log(Math.round(-2.5)); // -2
    - console.log(Math.round(2.499999999999999999999999999)); // 3
    - console.log(2.499999999999999999999999999 === 2.5); // true
- Math.max(x, y, z)	返回多个数中的最大值
- Math.min(x, y, z)	返回多个数中的最小值
- Math.pow(x,y)	返回 x 的 y 次幂(方))
- Math.sqrt()	对一个数进行开方运算
- Math.random()	生成 0-1 之间的随机数 包含0  不包含1 [0,1)
- Math.random()*100 向下取整  随机 0-99 范围 的整数
    - Math.floor(Math.random()*个数)+最小值     求任意范围的 随机 整数
### 逻辑运算符
- &&  与（ 且）： 两个都为真， 结果才为真。
- ||  或： 只要有一个是真， 结果就是真。
-  !  非： 对一个布尔值进行取反。
    - console.log(!0); // true  !存在隐式转换 会把0 先转换成布尔值,再取反
- &&  属于短路的与，如果第一个值为 false，则不会看第二个值。第一个值为true，会检查第二个值
- ||  属于短路的或，如果第一个值为 true，则不会看第二个值
#####  非布尔值进行与或运算时，会先将其转换为布尔值，然后再运算，但返回结果是原值
- 与运算的返回结果：（ 以两个非布尔值的运算为例） 遇到false就返回

    - 如果第一个值为 true， 则必然返回第二个值

    - 如果第一个值为 false， 则直接返回第一个值
### if判断
- if (条件表达式) {}
    - if 后边的 括号 具备隐式转换的功能(转换为布尔值)
    - 条件表达式 只有两种结果 true false 
    - 条件为真时，做的事情
- 第二种形式,条件分支语句 else
    - 为假做的事
    - 每一个else  都暗含了 之上的条件不满足
    - 跳楼现象
### 三元运算符
`4>3 ? alert('大') : alert('小');`
- 表达式?如果表达式结果为 true 执行这里的代码:如果表达式结果为 false 执行冒号后面的代码;
### swith语句
- switch (表达式) {
    - case 值1：
    - 语句体1;
    - break;
- 如果表达式与值都不匹配则:
    - default:
    - console.log('默认黑色');
    - break;
### Date创造时间
- new Date()获取当前时间
- var year = str.getFullYear(); 年
- var Month = str.getMonth(); 月
- var date = str.getDate(); 日
- var hours = str.getHours(); 时
- var min = str.getMinutes(); 分
- var sec = str.getSeconds(); 秒
- var sec1 = str.getMilliseconds(); 微秒
- console.log(dateTime.getTime());  距离 1970年 0时0分0秒  的  毫秒数
### for循环
- for (var i = 1; i <= 100; i++) {
        console.log(1);
    }
- 执行初始化表达式， 初始化变量（ 初始化表达式只会执行一次）

- 执行条件表达式， 判断是否执行循环：
- 如果为true， 则执行循环语句
- 如果为false， 终止循环

- 执行更新表达式， 更新表达式执行完毕继续重复
### while循环
- while (条件表达式) {
    - 语句...
    }
    var i = 1;
    while (i <= 10) {
        console.log(i);
        i++;
    }
- do...while 循环
    - do {
    - 语句...
    - } while (条件表达式)

    - 先执行在判断
     var n = 1;
        do {
            console.log(n);
            n++;
        } while (n <= 10)
#### break
- 用来跳出父类循环
- 不能跳出爷爷循环
#### continue
- 跳出当次循环 进行下一次循环
    