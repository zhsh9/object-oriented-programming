# Observer pattern

- motivation
  - seperate data and their presentation
  - example: excel data visualization
- implement
  - an observer can observe more than one subject
  - who triggers the update
    - subject
    - client
  - what hase been changed
    - push model
    - pull model
  - register obs only for specific events
    - void Subject::Attach(Observer *, Aspect &)

# Case: sort

- 需求定义
  - 概述：对一个文件的所有行进行排序
  - 支持运行的参数
    - -i
    - -n
    - -f k
    - -c k
    - -p [first | random | median3]
    - -r
  - 补充
    - field定义：一行中靠空格，TAB分割形成若干field
    - -i和-n，-n有效
    - -f和-c，-c有效
- 设计要求
  - 运行参数集中管理
  - 只能有一个对象来管理
  - 需要把运行参数的数据和函数封装起来
- singleton管理运行参数
- Input类的设计
- 应该具有的类
- 排序算法设计：快速排序
  - pivot值的选择影响算法效率

设计模式总结

- singleton
  - options, system_sort, compare_func_factory
- strategies
  - pivot_strategies and subclasses
- adaptor
  - sort_at_adaptor
- facade
  - system_sort