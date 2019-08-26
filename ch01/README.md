# Chapter 01

## 1.1

g++ -o test test.cpp

**-w** Inhibit all warning messages.

**-Wall** This enables all the warnings about constructions that some users consider questionable, and that are easy to avoid (or modify to prevent the warning), even in conjunction with macros.

## 1.2

```cpp
int main() {
 return -1;
}
```
echo $? return 255

Exit status out of range, refer to (this)[http://www.tldp.org/LDP/abs/html/exitcodes.html]

## 1.3

```cpp
#include<iostream>

int main() {
  std::cout<<"hello, world."<<std::endl;
}

```

## 1.4
```cpp
#include<iostream>

int main() {
  std::cout << "Please enter two number" <<std::endl;
  int v1=0, v2=0;
  std::cin >> v1 >> v2;
  std::cout << "The result of " << v1 << " and " << v2
	    << " is " << v1 * v2 <<std::endl;
  return 0;
}
```

## 1.5

```cpp
#include<iostream>

int main() {
  std::cout << "Please enter two number";
  std::cout << std::endl;
  int v1=0, v2=0;
  std::cin >> v1 >> v2;
  std::cout << "The result of ";
  std::cout << v1;
  std::cout << " and ";
  std::cout << v2;
  std::cout << " is ";
  std::cout << v1 * v2;
  std::cout << std::endl;
  return 0;
}
```

## 1.6
No... have to add std::cout, otherwise it does not have ostream object, and can not output or remove ';'

## 1.7
```cpp
/*
 * here is a wrong comment /* all */
 */

error: expected unqualified-id

```

## 1.8
1. yes
2. yes
3. no, error: expected expression, should add expression on the right, or just added a quote
4. yes, it treat /* "*/ and /*" */ as comment and the middle one " /* " as an expression

## 1.9

```cpp
#include<iostream>
 
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

## 1.10
```cpp
#include<iostream>
 
int main() {
  int sum=0, i=10;

  while(i >= 0) {
    std::cout << i << std::endl;
    --i;
  }
  return 0;
}

```
## 1.11
```cpp
#include<iostream>
 
int main() {
  std::cout << "Please enter two number" <<std::endl;
  int v1,v2;
  std::cin >> v1 >> v2;
  while (v1!=v2) {
    std::cout << v1<<std::endl;
    if(v1>v2) {
      v1--;
    } else {
      v1++;
    }
  }
  std::cout << v1 << std::endl;
  return 0;
}

```

## 1.12

count from -100 to 100, total is 0.


## 1.13

### q1
```cpp
#include<iostream>

int main() {
  int sum=0, i=50;

  for(; i<101; ++i) {
     sum += i;
  }
  std::cout << sum;
  return 0;
}
```
### q2
```cpp
#include<iostream>

int main() {
  int i=10;

  for(; i>=0; --i) {
    std::cout << i << std::endl;
  }

  return 0;
}

```

### q3

```cpp
#include<iostream>

int main() {
  std::cout << "Please enter two number" <<std::endl;
  int v1,v2;
  std::cin >> v1 >> v2;
  int big = v1, small=v2;
  if (big < small) {
    int tmp = big;
    big = small;
    small = tmp;
  }
  
  for( ;small!=big; ++small) {
     std::cout << small <<std::endl;
  }
  std::cout << small << std::endl;
  return 0;
}

```

## 1.14

for is more clear for simple condition loop, easy to detect increment condition

## 1.15
```cpp
// type error

//  error: cannot initialize a variable of type 'int' with an lvalue of
      type 'const char [6]'
      
int a = "hello";

// declaration error

// use of undeclared identifier 'a'

a = "hello";

```

## 1.16
```cpp
#include<iostream>

int main() {
  int sum = 0;
  int v1;
  while(std::cin >> v1) sum+=v1;
  std::cout << sum;
  return 0;
}

//mac ox using crt+d to end
```

## 1.17/1.18

```cpp
#include <iostream>
using namespace std;

int main() {

  int currVal = 0, val = 0;
  if (std::cin >> currVal) {
    int cnt = 1;
    while (std::cin >> val) {
      if (val == currVal)
	++cnt;
      else {
	std::cout << currVal << " occurs "
		  << cnt << " times " << std::endl;
	currVal = val;
	cnt = 1;
      }
    }
    std::cout << currVal << " occurs "
	      << cnt << " times " << std::endl; 
  }
  return 0;
}

```

all same value, will keep reading from terminal until the value changes
all different, will give result after every single input

## 1.19
see [1.14](#1.14)

## 1.20
```cpp
#include <iostream>
#include "Sales_item.h"

int main() {
  Sales_item book;
  while(std::cin >> book) std::cout << book <<std::endl;
  return 0;
}

```

## 1.21

```cpp
#include <iostream>
#include "Sales_item.h"

int main() {
  Sales_item book1, book2;
  std::cin >>book1>>book2;
  if(book1.isbn() == book2.isbn()) {
    std::cout << book1+book2 <<std::endl;
    return 0;
  } else {
    std::cerr << "These two ibsn is not same";
    return -1;
  }
}

```

## 1.22

```cpp
#include <iostream>
#include "Sales_item.h"

int main() {
  Sales_item book1, book2, total;
  if (std::cin >> book1) {
    total = book1;
    while(std::cin >> book2) {
    if(book1.isbn() == book2.isbn()) {
      total += book2;
    } else {
      std::cerr << "These books are not same" << std::endl;
      std::cout << total << std::endl;
      return -1;
    }
   }
    std::cout << total << std::endl;
    return 0;
  }
}

```
## 1.23

```cpp
#include <iostream>
#include "Sales_item.h"

int main() {
  Sales_item book1, book2, total;
  if (std::cin >> book1) {
    int cnt = 1;
    while(std::cin >> book2) {
    if(book1.isbn() == book2.isbn()) {
      ++cnt;
    } else {
      std::cout << cnt << std::endl;
      book1 = book2;
      cnt = 1;
    }
   }
    std::cout << cnt << std::endl;
    return 0;
  }
}

```

## 1.24

data:     
0-201-78345-X 3 20
{
      total += trans;
    } else {
      std::cout << total << std::endl;
      total = trans;
    }
   }
    std::cout << total << std::endl;
  } else {
    std::cerr << "No Data" << std::endl;
    return -1;
  }
  return 0;
}

```
