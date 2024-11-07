Для виведення інформації в консоль чи введення інформації з клавіатури можна використовувати оператори потокового вводу та виводу.

Щоб ними користуватись потрібно підключити бібліотеку "iostream". та вказати що ми в проекті будемо використовувати простір імен "std".


```c++
#include <iostream>//команда для підключення зовнішніх файлів
using namespace std;//команда призначена для використання простору імен по всьому проекту
```
---
cout = character out (оператор потокового виводу)

```c++
#include <iostream>
using namespace std;
int main()
{
	int y=5;
	cout<<"y = "<<y<<endl;
}
```

результат виконання:

>y = 5
---

cin = character in (оператор потокового виводу)

```c++
#include <iostream>
using namespace std;
int main()
{
	int y=0;
	cout<<"enter a number"<<endl;
	cin>>y;
	cout<<"y = "<<y<<endl;
}
```

результат виконання:

>enter a number
>8  // number 8 has been entered using keyboard
>y = 8
---