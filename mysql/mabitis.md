### mybatis和hibernate

轻量级（hibernate）高度封装

高复用（mybatis）高复用，可对高压环境进行优化

mybatis相对与jdbc，减少了重复代码的封装以及异常处理（jdbc每次都需要异常处理），且容易维护

### #{}和${}的区别

#{}可以预防sql注入，为参数占位符

${}为字符串替换，不进行预编译，会导致sql注入（但是一些场景（动态指定表）无法通过预编译进行替代，需要在代码层面进行防止sql注入）

###  mabitis缓存（一级缓存和二级缓存）

一级：仅限于会话层面的

二级：跨会话的缓存，作用域为整个mapper的namespace

### 自带的链接池（核心，利用两个list记录空闲的链接和使用的链接）

jdbc在建立一个链接后会进行关闭

mybatis基于jdbc，在使用链接之后不是进行关闭而是将链接归还到链接池中

### 动态sql

### 延迟加载（懒加载）

可以在config中进行配置

在复杂关系的数据库中可以加速项目的第一次导入（就会避免很多插件的第一次启动十分的慢）

### 实现一个插件（实现mybatis的inyerceptor接口）

实现插件的逻辑是-实现拦截器（实现切入的逻辑）-将切入器进行注册

mabitis中存在拦截器链（加载方式为初次加载时会解析文件），

#### interceptor chain（责任链模式）

mybatis在进行每一个拦截方法的分析时，会依次进行所有拦截器的内容，直到拦截器都被执行完毕

### 如何实现数据库类型和java类进行转换的

在type中进行了多个typehander的实现（真多啊）


