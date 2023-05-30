在C++中，explicit是一个关键字，可以用于修饰构造函数，表示该构造函数只能用于显式转换，不能用于隐式转换。

在没有使用explicit关键字的情况下，可以使用一个参数的构造函数进行隐式转换，例如：

```
class MyClass {
public:
  MyClass(int value) : m_value(value) {}
private:
  int m_value;
};

void func(MyClass obj) {
  // ...
}

int main() {
  func(123);  // 隐式转换
  return 0;
}
```
在这个例子中，MyClass类有一个参数为int类型的构造函数，可以用于隐式转换。在main函数中，将整数123作为参数传给func函数，这个整数会被隐式转换成MyClass对象，然后作为参数传递给func函数。
使用explicit关键字可以防止这种情况的发生，例如：

```
class MyClass {
public:
  explicit MyClass(int value) : m_value(value) {}
private:
  int m_value;
};

void func(MyClass obj) {
  // ...
}

int main() {
  func// 使用explicit关键字，禁止隐式转换
  func(MyClass(123));  // 显式转换
  return 0;
}
```
在这个例子中，MyClass类的构造函数使用了explicit关键字，表示该构造函数只能用于显式转换。在main函数中，调用func函数时，需要显式地将整数123转换成MyClass对象，然后作为参数传递给func函数。
使用explicit关键字可以避免一些隐式转换带来的不必要的错误和风险，可以提高代码的可读性和安全性。
