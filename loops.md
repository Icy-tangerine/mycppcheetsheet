### цикл while

використовується коли потрібно повторювати блок коду певну кількість разів

while("*умова*"){
	"*тіло циклу*"
}

по принципу роботи аналогічний коду:

```c++
#include <iostream>
int main(){
	int i=0;
	f1:
	if(i<10){
		i++;
		std::cout<<i<<std::endl;
		goto f1;
	}
}
```

```c++
#include <iostream>
int main(){
	int i=0;
	while(i<10){
		i++;
		std::cout<<i<<std::endl;
	}
}
```

>1

>2

>3

>4

>5

>6

>7

>8

>9

>10

https://en.cppreference.com/w/cpp/language/while

---

### цикл for

зазвичай використовується коли потрібно ітеруватись по контейнеру даних чи по значеннях функції

for("*початкове значення*" ; "*умова*" ; "*крок*"){
	"*тіло циклу*"
}


```c++
#include <iostream>
#include "math.h"
int main(){
	for(float i=0;i<3.14;i+=(3.14159265258979/10))
	{
		std::cout<<sin(i)<<std::endl;
	}
}
```

>0

>0.308866

>0.587528

>0.808736

>0.950859

>1

>0.951351

>0.809672

>0.588816

>0.31038

>0.00159302


https://en.cppreference.com/w/cpp/language/for