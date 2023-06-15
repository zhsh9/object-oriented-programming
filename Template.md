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

