# Chapter 02

## 2.1
Minimum size of these type are different.
C++ guarantees short and int is at least 16 bits, long at least 32 bits, long long at least 64 bits.

Unsigned type represents numbers that are equal to or bigger than zero while signed type represents positive number
and negative number and zero.

As the name implies, a double has 2x the precision of float. In general,
a double has 15 decimal digits of precision, while float has 7.

refer to [here](https://stackoverflow.com/questions/2386772/what-is-the-difference-between-float-and-double)

## 2.2

Using `double`, or `float`.
- The rate most like that: 2.3% per year.
- The principal most like that: $900.16
- The payment most like that: $2131.21

## 2.3
32
int - 32 bits, 4294967296(2^32 - 32)
32
-32
0
0

## 2.4
```cpp
#include <iostream>

int main() {
  unsigned u = 10, u2 = 42;
  std::cout << u2 - u << std::endl;
  std::cout << u - u2 << std::endl;

  int i=10, i2 = 42;
  std::cout << i2 - i << std::endl;
  std::cout << i - i2 << std::endl;
  std::cout << i - u << std::endl;
  std::cout << u - i << std::endl;
}
```

## 2.5
a. char, wchar_t, string, <mark>string wide character literal</mark>

b. <mark>decimal, unsigned decimal, long decimal, unsigned long decimal, octal, hexadecimal</mark>

c. float, float, long double

d. <mark>decimal, unsigned decimal,</mark> double, double

## 2.6
yes, first one is decimal, second one is octal.

<mark>int month = 09 is invalid, cause octal don't have digit 9.</mark>

## 2.7
a. Who goes with Fergus?(new line) `string`

b. 31.4 `long`

c. 1024 `float`

d. 3.14 `long double`

## 2.8

```cpp
#include <iostream>

int main() {
  std::cout <<"\062\x4d\n";
  std::cout <<"\062\t\x4d\n";
}
```

## 2.9
a. >> should be followed by value,
```cpp
int input_value = 0;
std::cin >> input_value;
```

b. compiler will show error, it should be int i(3.14) or double i = {3.14};

c. The `wage` is  not defined yet, it should be `double salary = 9999.99, wage = salary;`

d. `int i=3.14;` it is equal to `int i=3;`, it should use `double i=3.14` if try to keep decimal

## 2.10
- `global_str`: empty string
- `global_int`: 0
- `local_int`: uninitialized
- `local_str`: empty string

## 2.11

- definition
- definition
- declaration

## 2.12
a. no, `double` is keyword

b. ok

c. must be underline

d. can not use or, as it is operator replacement

e. ok

## 2.13
i=100

## 2.14
legal, i = 100, sum = 45

## 2.15
b, initialization of a reference should be an object

d it should be initialized
## 2.16
all ok, type tranfer.
## 2.17
10, 10

## 2.18
```cpp
#include <iostream>

int main() {
  int *p1, *p2;
  int v1=2, v2=3;
  p1 = &v1;
  p2 = &v2;

  std::cout << "p1 " << p1 << std::endl;
  std::cout << "p2 " << p2 << std::endl;

  // change p1 value
  p1 = &v2;

  std::cout << "p1 " << p1 << std::endl;
  std::cout << "p2 " << p2 << std::endl;

  // change v2 value, as p1 has already pointed to v2
  *p1 = 10;
  std::cout << "p1 " << p1 << std::endl;
  std::cout << "v2 " << v2 << std::endl;

  // p1 0x7ffee34d07a4
  // p2 0x7ffee34d07a0
  // p1 0x7ffee34d07a0
  // p2 0x7ffee34d07a0
  // p1 0x7ffee34d07a0
  // v2 10

  return 0;
}
```

## 2.19

Point is an object and it could point to different object, but reference is not an object, it needs to be initialized once it has been declared and it will be bind with the object it refer to. Basically, reference is the alias of another object but point is a place to store address of a variable

## 2.20
the value of i is equal to 42*42

## 2.21
a. illegal, as dp is a point pointing to double type.

b. illegal, as we can not assign int variable directly to point, even it is zero

c. ok

## 2.22
1. always true <mark>wrong, whether p is nullptr</mark>

2. it depends on the value of *p, it will show error if the point is not pointing any object

## 2.23
no.. as the value of an object may be address
<mark>No. Because more information needed to determine whether the pointer is valid or not.</mark>

## 2.24
void * could store any tyoe of point, but lp is long point while i is int type

## 2.25
a.
   - ip -> int point
   - i -> int
   - r -> reference

b.
   - i -> int
   - ip -> nullptr

c.
   - ip -> int point
   - ip2 -> int

## 2.26
1. need to be initialized
2. yes
3. yes
4. no, const can not be changed

## 2.27
a. the initial value must be object

b. yes

c. the initial value must be object

d. yes

e. yes

f. const has to be initialized first <mark> illegal, r2 is a reference that cannot be const.</mark>

g. yes

## 2.28
a. const need to be initialized

b. const need to be initialized

c. const need to be initialized

d. const need to be initialized

e. illegal, const need to be initialized
<mark>legal, it is a point pointing to const int</mark>

## 2.29
a. yes

b. no

c. yes <mark>illegal. ic is a const int.</mark>

d. no

e. no

f. no

## 2.30

v2 -> top

p2 -> low

p3 -> top

r2 -> low
## 2.31
1. wrong <mark>legal, top-level const in v2 is ignored.</mark>

2. wrong, const; right

3. wrong, type error; right

## 2.32

*p = nullptr

## 2.33

- 42
- 42
- cant assign value to const <mark>wrong, should be 42</mark>
- cant point to a non-object `error: assigning to 'int *' from incompatible type 'int'`
- cant point to a non-object `error: assigning to 'const int *' from incompatible type 'int'`
- error, cant assign value to const `note: variable 'g' declared const here`

## 2.34

```cpp
#include <iostream>

int main() {
  int i=0, &r = i;
  auto a = r;
  const int ci = i, &cr = ci;
  auto b = ci;
  auto c = cr;
  auto d = &i;
  auto e = &ci;
  auto &g = ci;
  a = 42;
  std::cout << a << std::endl;
  b = 42;
  std::cout << b << std::endl;
  c = 42;
  std::cout << c << std::endl;
  // d = 42;
  std::cout << d << std::endl;
  // e = 42;
  std::cout << e << std::endl;
  g = 42;
  std::cout << g << std::endl;
  return 0;
}
```
## 2.35
- type of j is `const int`;
- j is `int`; <mark>wrong, type is int, top level const will be ignored</mark>
- k is reference of i, type is `const int `; <mark> wrong, type is `const int &`</mark>
- p is point pointing to `const int`; <mark>wrong, type is `const int *`</mark>
- type of j2 is `const int`;
- k2 is reference of i, and type is `const int`; <mark>wrong, type is `const int &`</mark>

## 2.36
- a -> int; b -> int; c -> int; d -> 'int &';
- a=4; b=4; c=4; d=4;

## 2.37
c=3; d=3

## 2.38

decltype will not ingore top level const, auto will ignore top level const

<mark>another diff between decltype and auto is that the deduction done by decltype depends on the form of its given expression.
</mark>

same:
```cpp
int a = 0;
decltype(a) b; //int
auto c = a; //int
```

diff:
```cpp
const int a = 0;
decltype(a) b; // const int
auto c = a; //int
```

## 2.39
```cpp
struct Foo { /* empty  */ } // Note: no semicolon
int main()
{
   return 0;
}
```
error: expected ';' after struct

## 2.40
```cpp
Sales_item {
  std::string bookName;
  std::string bookNo;
  unsigned unitsSold = 0;
  unsigned double price;
  double sum = 0.0;
};
```
## 2.41

### 1.51

```cpp
#include <iostream>
#include <string>

struct Sales_data {
  std::string bookNo;
  unsigned unit = 0;
  double revenue = 0.0;
};

int main() {
  Sales_data item;
  double price;
  std::cin >> item.bookNo >> item.unit >> price;
  item.revenue = price * item.unit;
  std::cout << item.bookNo << " "
  << item.unit <<" "
  <<  price <<" "
   << item.revenue;
  return 0;
}
```

```cpp
#include <iostream>
#include <string>

struct Sales_data {
  std::string bookNo;
  unsigned unit = 0;
  double revenue = 0.0;
};

int main() {
  Sales_data book1, book2;
  double price1, price2;
  std::cin >> book1.bookNo >> book1.unit >> price1;
  std::cin >> book2.bookNo >> book2.unit >> price2;
  if(book1.bookNo == book2.bookNo) {
    std::cout << book1.bookNo << " " << book1.unit+book2.unit
    << " " << book1.unit * price1+book2.unit * price2
    <<std::endl;
    return 0;
  } else {
    std::cerr << "These two ibsn is not same";
    return -1;
  }
}
```
### 1.52
```cpp
add later
```
### 1.6
```cpp
add later
```
## 2.42
