# Chapter 03

## 3.1
### 1.9

```cpp
#include<iostream>
using std::cout;

int main() {
  int sum=0, i=50;

  while(i<101) {
    sum += i;
    ++i;
  }
  std::cout << sum;
  return 0;
}
// output is 3825
```

### 1.10
```cpp
#include<iostream>
using std::cout; using std::endl;

int main() {
  int sum=0, i=10;

  while(i >= 0) {
    cout << i << endl;
    --i;
  }
  return 0;
}

```
### 1.11
```cpp
#include<iostream>
using std::endl;
using std::cout;
using std::cin;

int main() {
  cout << "Please enter two number" <<endl;
  int v1,v2;
  cin >> v1 >> v2;
  while (v1!=v2) {
    cout << v1<<std::endl;
    if(v1>v2) {
      v1--;
    } else {
      v1++;
    }
  }
  cout << v1 << endl;
  return 0;
}
```
### 2.42

Sales_data.h file

```cpp
#ifndef SALES_DATA_H
#define SALES_DATA_H
#include <string>
struct Sales_data {
  // should not using `using` in the head file
  std::string bookNo;
  unsigned unit = 0;
  double revenue = 0.0;
};
#endif

```

main file
```cpp
#include <iostream>
#include <string>
#include "Sales_data.h"

using std::cin;
using std::cout;
using std::endl;
using std::cerr;

int main() {
  Sales_data book1, book2;
  double price1, price2;
  cin >> book1.bookNo >> book1.unit >> price1;
  cin >> book2.bookNo >> book2.unit >> price2;
  if(book1.bookNo == book2.bookNo) {
    cout << book1.bookNo << " " << book1.unit+book2.unit
    << " " << book1.unit * price1+book2.unit * price2
    <<endl;
    return 0;
  } else {
    cerr << "These two ibsn is not same";
    return -1;
  }
}
```
