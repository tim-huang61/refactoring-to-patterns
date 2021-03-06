
### 将创建知识搬移到 Factory

- Factory 定义

  - 实现一个或多个 Creation Method 的类就称为 Factory

- 动机

  - 当创建一个对象的知识散布在多个类中
  - 创建蔓延问题

    - 将创建的职责放在了不应该承担对象创建任务的类中

- 实现

  - 使用一个类封装创建逻辑和客户代码的实例化/配置选项
  - 客户代码可以告诉 Factory 实例如何实例化/配置一个对象
  - 然后用同一个 Factory 实例在运行时执行实例化/配置

- 优点

  - 合并创建逻辑和实例化/配置选项
  - 将客户代码与创建逻辑解耦

- 缺点

  - 如果可以直接实例化，会使设计复杂化

- 做法

  - 以下做法假设 Factory 将实现一个类，而不是类要实现的接口

  - 1. 实例化类就是一个与其他类合作实例化产品（即某个类的实例）的类

    - 需要用 Creation Method 来实例化产品

  - 2. 创建一个将成为工厂的新类，根据工厂所创建的产品给它命名

  - 3. 应用搬移方法重构将 Creation Method 搬移到工厂类中

    - 如果 Creation Method 是静态的，需要改为非静态的

  - 4. 将实例化类更新为实例化工厂对象，并调用工厂对象获取类的实例

  - 5. 在实例化中仍然使用其他类的数据和方法。

    - 将可用的任何东西搬移到工厂类中，这样它就能够尽可能多地处理创建工作

- 扩展

  - 如果创建逻辑过于复杂，就应该将其改为 Abstract Factory 模式

    - 支持太多创建选项
- 视频

[重构与模式 - Factory](https://www.bilibili.com/video/BV1X7411S7ho/)