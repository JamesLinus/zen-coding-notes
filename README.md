禅意编程札记
============

## 基本编码习惯
- 代码自描述
  - 代码是写给其他人看的，不是写给机器看的
- 每条语句皆有作用，不做无谓的赋值
- 减少上下文依赖，编写显而易见是正确的代码
- 类内尽量少维护状态变量
- 最小化参数要求
  - 传ID就能解决问题的时候不需要传对象
- 减少函数内多余的中间变量
  - 减少中间变量的命名的意义
  - 直接return
- 在一个作用域内，变量的类型保持不变(仅对脚本语言)

## 项目工程
- 如果你的整体代码结构变得极其复杂，往往是产品需求有问题
- 从整体到细节，自顶向下的工作顺序
  - 基础库的编写顺序，优先写 guide / example
- 全新的业务工程，先不考虑架构
- 好的代码不是写出来的，是重构出来的
  - 在项目发展的合适时机进行重构，项目规划过程中应该留出明确的重构时间
  - 这份札记是如何编写出来的
  - 重构的过程中不一定要保证每次修改均可运行

## 逻辑控制结构
- 防御式编程
- 循环结构优化
  - 不同的语言有不同的最佳实践
- 不要轻易使用while(true)
- 错误是常态，错误处理像业务代码本身一样必不可少

## 代码拆分规则
- 原子化函数
  - 举例，微博三步授权流程代码
- 业务逻辑分层
- 类的层次
- 什么样的代码应该写在控制层，什么样的代码应该写在公共流程中(并加启用条件)
- 不要把业务相关代码和基础库代码混在一起
  - 始终以要开源的标准去写基础库，绝不耦合业务逻辑
- 一个功能全面的大方法还是多个功能简单的小方法
  - 与其用复杂的配置参数，不如用多个简单的原子化方法
  - 然后写一个通过多个原子化方法实现功能的shorthand方法
- 除非有特别需求，提供一种初始化/配置方法就够了，不要玩参数列表的花活
- 一个可以处理多种情况的多if-else函数，还是处理单一情况的简单函数
- 区分有状态对象和无状态对象
- shorthand方法
- 不要在局部函数里修改全局变量，如果不得不这么做，请明确声明
- 如果你很难给某个方法起名字，往往是因为代码拆分有问题
- 对于脏的输入，在明确一层代码中做参数校验，而在后续的代码层中完全信任传入的参数，因为都已经被校验过

## 复用，还是冗余？
- 什么样的代码应该写成函数？
  - 不是代码写了两遍就需要写成函数，而是这个函数有明确的功能和清晰的参数列表
  - 不要因为一段代码只写过一遍，就不抽成函数
- 合理冗余代码
  - DRY原则永远是对的吗？
  - 明智而自豪地复制代码
- 三行以内的代码不值得复用
- 恶心自己，方便大家
  - 类的内部合理冗余代码，外部调用足够简单

## 命名
- 变量名的原则
- 变量的命名要符合上下文场景
- 学好英语，起好名字
  - 用意义准确的特殊词，少用组合词，比如: SiteUser -> Member
  - 正确使用单复数
  - 梳理出明确的命名原则

## 注释
- Don't comment WHAT, comment WHY.
- 不要寄希望于用注释来解释清楚代码
- 和业务相关的脏代码必须注释
- 删除历史遗留代码，而不要注释它

## 面向对象的设计原则
- 多层继承还是多个独立的类
  - 尽量在一个类中呈现出完整的业务逻辑，同一个层次的业务逻辑，不要写在不同层的类中
  - 多层继承的代码可读性和可维护性远比你想象得要糟
- 善用trait/mixin
- 每一个public函数的切面，整个对象状态都自洽
- 将对成员变量的变更和维护，集中到有限几个函数中，原子化的功能函数不维护状态变量

## 目录结构和文件命名
- 用唯一确定的属性作为定位的规则，避免歧义
  - 按层放置文件
- 文件名和类名有一致的对应规则

## PHP技巧
- spl库的运用
- yield的运用
- 命名空间的运用

## Javascript技巧


## Web服务技巧

