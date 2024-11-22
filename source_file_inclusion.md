

```c++
#include <h-char-sequence>
#include "q-char-sequence"
```
шукає файл за вказаною назвою і заміняє цю строку наповненням цього файлу.

>файл lib.cpp
```c++
int number=5;
```
>файл test.cpp
```c++
#include <iostream>
#icnlude "lib.cpp"
int main(){
	std::cout<<number<<std::endl;
}
```
>5



```c++
test
```
