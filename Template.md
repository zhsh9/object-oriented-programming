# 模板特化 (Template Speciliazation)

![image-20230616065249727](.Template.assets/image-20230616065249727.png)

- 全部特化
- 部分特化

# 类型萃取 (Type Traits)

```c++
template <typename T>
struct traits {};

template <>
struct traits<float> {
    static inline float epsilon() {
        return FLT_EPSILON;
    }
};

template <>
struct traits<double> {
    static inline double epsilon() {
        return DBL_EPSILON;
    }
};

template <typename T>
class matrix {
  public:
    inline T epsilon() {
        return traits<T>::epsilon();
    }
};
```

# 类型分类技术 (Type Classification)

随着 T 所取类型的不同，该模板会做不同的处理

```c++
template <typename T>
class Typelnfo {
  public:
    enum { lsPtrT = 0, IsRefT = 0, IsArrayT = 0 };
    typedef T baseT;
    typedef T bottomT;
};

template <typename T>
class Typelnfo<T*> {
  public:
    enum { lsPtrT = 1, lsRefT = 0, lsArrayT = 0 };
    typedef T baseT;
    typedef typename Typelnfo<T>::bottomT bottomT;
};

template <typename T>
class Typelnfo<T&> {
  public:
    enum { lsPtrT = 0, lsRefT = 1, IsArrayT = 0 };
    typedef T baseT;
    typedef typename Typelnfo<T>::bottomT bottomT
};

template <typename T, size_t N>
class Typelnfo<T[N]> {
  public:
    enum { lsPtrT = 0, lsRefT = 0, IsArrayT = 1 };
    typedef T baseT;
    typedef typename Typelnfo<T>::bottomT bottomT;
};
```

# CRTP模式

ref: 正向成长, https://juejin.cn/post/7121364810058432549

CRTP, Curiously Recurring Template Pattern(奇特的递归模板模式)代表了类实现技术中一种通用的模式，即派生类将本身作为模板参数传递给基类。它的实现形式有：

1. 最简单的情形。CRTP有一个非依赖型基类`Curious`不是模板，因此免于与依赖型基类`CuriousBase`的名字可见性等问题纠缠

```c++
template <typename Derived>
class CuriousBase {
    ......
};
class Curious : public CuriousBase<Curious> {
    ......
};
```

2. 非依赖型基类是模板

```c++
template <typename Derived>
class CuriousBase {
    ......
};
template <typename T>
class CuriousTemplate : public CuriousBase<CuriousTemplate<T> > {
    ......
};
```

3. 模板的模板参数

```c++
template <template<typename> class Derived>
class MoreCuriousBase {
    ......
};
template <typename T>
class MoreCurious : public MoreCuriousBase<MoreCurious>{ 
    ......
};
```
